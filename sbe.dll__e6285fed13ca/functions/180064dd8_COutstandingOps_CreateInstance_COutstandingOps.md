# COutstandingOps::CreateInstance(COutstandingOps * *)

- ea: `0x180064dd8`
- end: `0x180064e67`
- name: `?CreateInstance@COutstandingOps@@SAKPEAPEAV1@@Z`
- size: `143`
- prototype: `unsigned int __fastcall(struct COutstandingOps **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180063224`
- `0x180063528`
- `0x18007776c`

## callees

- `0x1800017a0`
- `0x180063e9c`
- `0x180064dd8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180064e1c`
- `KERNEL32!CreateEventW` at `0x180064e1c`
- `KERNEL32!InitializeCriticalSection` at `0x180064e0b`
- `KERNEL32!InitializeCriticalSection` at `0x180064e0b`
- `KERNEL32!GetLastError` at `0x180064e2b`
- `KERNEL32!GetLastError` at `0x180064e2b`

## pseudocode

```c
__int64 __fastcall COutstandingOps::CreateInstance(struct COutstandingOps **a1)
{
  char *v2; // rax
  struct COutstandingOps *v3; // rbx
  DWORD LastError; // edi
  HANDLE EventW; // rax
  unsigned int v6; // edx

  v2 = (char *)operator new(0x40u);
  v3 = (struct COutstandingOps *)v2;
  if ( !v2 )
  {
    LastError = 8;
    goto LABEL_8;
  }
  LastError = 0;
  *(_DWORD *)v2 = 0;
  *((_QWORD *)v2 + 1) = 0;
  *((_DWORD *)v2 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v2 + 24));
  EventW = CreateEventW(0, 1, 1, 0);
  *((_QWORD *)v3 + 1) = EventW;
  if ( !EventW )
    LastError = GetLastError();
  *a1 = v3;
  if ( LastError )
  {
    COutstandingOps::`scalar deleting destructor'(v3, v6);
LABEL_8:
    *a1 = 0;
    return LastError;
  }
  _InterlockedIncrement((volatile signed __int32 *)v3);
  return LastError;
}

```

## disassembly

```asm
0x180064dd8  mov     [rsp+arg_0], rbx
0x180064ddd  mov     [rsp+arg_8], rsi
0x180064de2  push    rdi
0x180064de3  sub     rsp, 20h
0x180064de7  mov     rsi, rcx
0x180064dea  mov     ecx, 40h ; '@'; Size
0x180064def  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064df4  mov     rbx, rax
0x180064df7  test    rax, rax
0x180064dfa  jz      short loc_180064E49
0x180064dfc  xor     edi, edi
0x180064dfe  lea     rcx, [rax+18h]; lpCriticalSection
0x180064e02  mov     [rax], edi
0x180064e04  mov     [rax+8], rdi
0x180064e08  mov     [rax+10h], edi
0x180064e0b  call    cs:__imp_InitializeCriticalSection
0x180064e11  lea     edx, [rdi+1]; bManualReset
0x180064e14  xor     r9d, r9d; lpName
0x180064e17  mov     r8d, edx; bInitialState
0x180064e1a  xor     ecx, ecx; lpEventAttributes
0x180064e1c  call    cs:__imp_CreateEventW
0x180064e22  mov     [rbx+8], rax
0x180064e26  test    rax, rax
0x180064e29  jnz     short loc_180064E33
0x180064e2b  call    cs:__imp_GetLastError
0x180064e31  mov     edi, eax
0x180064e33  mov     [rsi], rbx
0x180064e36  test    edi, edi
0x180064e38  jz      short loc_180064E44
0x180064e3a  mov     rcx, rbx; this
0x180064e3d  call    ??_GCOutstandingOps@@AEAAPEAXI@Z; COutstandingOps::`scalar deleting destructor'(uint)
0x180064e42  jmp     short loc_180064E4E
0x180064e44  lock inc dword ptr [rbx]
0x180064e47  jmp     short loc_180064E55
0x180064e49  mov     edi, 8
0x180064e4e  mov     qword ptr [rsi], 0
0x180064e55  mov     rbx, [rsp+28h+arg_0]
0x180064e5a  mov     eax, edi
0x180064e5c  mov     rsi, [rsp+28h+arg_8]
0x180064e61  add     rsp, 20h
0x180064e65  pop     rdi
0x180064e66  retn
```
