# timeThread

- ea: `0x18000f260`
- end: `0x18000f2f4`
- name: `timeThread`
- size: `148`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001bc0`
- `0x180002140`
- `0x18000d470`
- `0x18000f260`

## import_xrefs

- `ntdll!NtWaitForMultipleObjects` at `0x18000f2d5`
- `ntdll!NtWaitForMultipleObjects` at `0x18000f2d5`

## pseudocode

```c
void __fastcall __noreturn timeThread(PVOID Parameter)
{
  NTSTATUS v1; // eax
  ULONG Count[4]; // [rsp+30h] [rbp-108h] BYREF
  _DWORD v3[20]; // [rsp+40h] [rbp-F8h] BYREF
  HANDLE Object[18]; // [rsp+90h] [rbp-A8h] BYREF

  Count[0] = 0;
  memset_0(Object, 0, 0x88u);
  dword_180026970 = 1;
  while ( 1 )
  {
    InitializeWaitEventArrays(Count, Object, v3);
    while ( 1 )
    {
      v1 = NtWaitForMultipleObjects(Count[0], Object, WaitAny, 1u, 0);
      if ( !v1 )
        break;
      if ( (unsigned int)(v1 - 1) <= 0xF )
        TimerCompletion(v3[v1]);
    }
  }
}

```

## disassembly

```asm
0x18000f260  sub     rsp, 138h
0x18000f267  mov     rax, cs:__security_cookie
0x18000f26e  xor     rax, rsp
0x18000f271  mov     [rsp+138h+var_18], rax
0x18000f279  xor     edx, edx; Val
0x18000f27b  mov     [rsp+138h+Count], 0
0x18000f283  mov     r8d, 88h; Size
0x18000f289  lea     rcx, [rsp+138h+Object]; void *
0x18000f291  call    memset_0
0x18000f296  mov     cs:dword_180026970, 1
0x18000f2a0  lea     r8, [rsp+138h+var_F8]
0x18000f2a5  lea     rdx, [rsp+138h+Object]
0x18000f2ad  lea     rcx, [rsp+138h+Count]
0x18000f2b2  call    InitializeWaitEventArrays
0x18000f2b7  mov     ecx, [rsp+138h+Count]; Count
0x18000f2bb  lea     rdx, [rsp+138h+Object]; Object
0x18000f2c3  mov     r9b, 1; Alertable
0x18000f2c6  mov     [rsp+138h+Time], 0; Time
0x18000f2cf  mov     r8d, 1; WaitType
0x18000f2d5  call    cs:__imp_NtWaitForMultipleObjects
0x18000f2db  mov     ecx, eax
0x18000f2dd  test    eax, eax
0x18000f2df  jz      short loc_18000F2A0
0x18000f2e1  lea     eax, [rcx-1]
0x18000f2e4  cmp     eax, 0Fh
0x18000f2e7  ja      short loc_18000F2B7
0x18000f2e9  mov     ecx, [rsp+rcx*4+138h+var_F8]
0x18000f2ed  call    TimerCompletion
0x18000f2f2  jmp     short loc_18000F2B7
```
