# CPVRAsyncReader::GetWaitObject_(void)

- ea: `0x180079a28`
- end: `0x180079ad3`
- name: `?GetWaitObject_@CPVRAsyncReader@@AEAAPEAVCWait@@XZ`
- size: `171`
- prototype: `struct CWait *__fastcall(CPVRAsyncReader *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180079678`
- `0x18007aed4`

## callees

- `0x1800017a0`
- `0x180016a74`
- `0x180078714`
- `0x180079a28`

## import_xrefs

- `KERNEL32!ResetEvent` at `0x180079ab3`
- `KERNEL32!ResetEvent` at `0x180079ab3`
- `KERNEL32!CreateEventW` at `0x180079a85`
- `KERNEL32!CreateEventW` at `0x180079a85`
- `KERNEL32!GetLastError` at `0x180079a94`
- `KERNEL32!GetLastError` at `0x180079a94`

## pseudocode

```c
struct CWait *__fastcall CPVRAsyncReader::GetWaitObject_(CPVRAsyncReader *this)
{
  struct CWait **v1; // rcx
  struct CWait *v2; // rbx
  struct CWait *v3; // rax
  DWORD LastError; // edi
  HANDLE EventW; // rax
  unsigned int v6; // edx
  void *v7; // rcx

  v1 = (struct CWait **)((char *)this + 24);
  v2 = *v1;
  if ( *v1 == (struct CWait *)v1 )
  {
    v3 = (struct CWait *)operator new(0x28u);
    v2 = v3;
    if ( v3 )
    {
      *((_QWORD *)v3 + 2) = 0;
      LastError = 0;
      *((_DWORD *)v3 + 6) = 0;
      *((_QWORD *)v3 + 4) = 0;
      *((_QWORD *)v3 + 1) = v3;
      *(_QWORD *)v3 = v3;
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)v2 + 2) = EventW;
      if ( !EventW )
        LastError = GetLastError();
      if ( !LastError )
        goto LABEL_7;
      CWait::`scalar deleting destructor'(v2, v6);
    }
    return 0;
  }
  CWait::ListRemove(*v1);
LABEL_7:
  v7 = (void *)*((_QWORD *)v2 + 2);
  *((_DWORD *)v2 + 6) = 0;
  *((_QWORD *)v2 + 4) = 0;
  ResetEvent(v7);
  return v2;
}

```

## disassembly

```asm
0x180079a28  mov     [rsp+arg_0], rbx
0x180079a2d  push    rdi
0x180079a2e  sub     rsp, 20h
0x180079a32  add     rcx, 18h
0x180079a36  mov     rbx, [rcx]
0x180079a39  cmp     rbx, rcx
0x180079a3c  jz      short loc_180079A48
0x180079a3e  mov     rcx, rbx; struct CWait *
0x180079a41  call    ?ListRemove@CWait@@SAXPEAV1@@Z; CWait::ListRemove(CWait *)
0x180079a46  jmp     short loc_180079AA0
0x180079a48  mov     ecx, 28h ; '('; Size
0x180079a4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180079a52  mov     rbx, rax
0x180079a55  test    rax, rax
0x180079a58  jz      short loc_180079AC3
0x180079a5a  mov     qword ptr [rax+10h], 0
0x180079a62  xor     edi, edi
0x180079a64  mov     dword ptr [rax+18h], 0
0x180079a6b  xor     r9d, r9d; lpName
0x180079a6e  mov     qword ptr [rax+20h], 0
0x180079a76  xor     r8d, r8d; bInitialState
0x180079a79  xor     ecx, ecx; lpEventAttributes
0x180079a7b  mov     [rax+8], rax
0x180079a7f  lea     edx, [rdi+1]; bManualReset
0x180079a82  mov     [rax], rax
0x180079a85  call    cs:__imp_CreateEventW
0x180079a8b  mov     [rbx+10h], rax
0x180079a8f  test    rax, rax
0x180079a92  jnz     short loc_180079A9C
0x180079a94  call    cs:__imp_GetLastError
0x180079a9a  mov     edi, eax
0x180079a9c  test    edi, edi
0x180079a9e  jnz     short loc_180079ABB
0x180079aa0  mov     rcx, [rbx+10h]; hEvent
0x180079aa4  mov     dword ptr [rbx+18h], 0
0x180079aab  mov     qword ptr [rbx+20h], 0
0x180079ab3  call    cs:__imp_ResetEvent
0x180079ab9  jmp     short loc_180079AC5
0x180079abb  mov     rcx, rbx; this
0x180079abe  call    ??_GCWait@@QEAAPEAXI@Z; CWait::`scalar deleting destructor'(uint)
0x180079ac3  xor     ebx, ebx
0x180079ac5  mov     rax, rbx
0x180079ac8  mov     rbx, [rsp+28h+arg_0]
0x180079acd  add     rsp, 20h
0x180079ad1  pop     rdi
0x180079ad2  retn
```
