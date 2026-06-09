# ResumeImpersonate(void * *)

- ea: `0x180010880`
- end: `0x1800108db`
- name: `?ResumeImpersonate@@YAKPEAPEAX@Z`
- size: `91`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000e7d0`
- `0x18000f710`

## callees

- `0x180010880`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800108a9`
- `KERNEL32!GetLastError` at `0x1800108a9`
- `KERNEL32!CloseHandle` at `0x1800108ba`
- `KERNEL32!CloseHandle` at `0x1800108ba`
- `ADVAPI32!SetThreadToken` at `0x180010899`
- `ADVAPI32!SetThreadToken` at `0x180010899`

## pseudocode

```c
__int64 __fastcall ResumeImpersonate(void **a1)
{
  DWORD LastError; // edi

  LastError = 0;
  if ( *a1 )
  {
    if ( !SetThreadToken(0, *a1) )
      LastError = GetLastError();
    CloseHandle(*a1);
    *a1 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x180010880  mov     [rsp+arg_0], rbx
0x180010885  push    rdi
0x180010886  sub     rsp, 20h
0x18001088a  mov     rdx, [rcx]; Token
0x18001088d  xor     edi, edi
0x18001088f  mov     rbx, rcx
0x180010892  test    rdx, rdx
0x180010895  jz      short loc_1800108CD
0x180010897  xor     ecx, ecx; Thread
0x180010899  call    cs:__imp_SetThreadToken
0x1800108a0  nop     dword ptr [rax+rax+00h]
0x1800108a5  test    eax, eax
0x1800108a7  jnz     short loc_1800108B7
0x1800108a9  call    cs:__imp_GetLastError
0x1800108b0  nop     dword ptr [rax+rax+00h]
0x1800108b5  mov     edi, eax
0x1800108b7  mov     rcx, [rbx]; hObject
0x1800108ba  call    cs:__imp_CloseHandle
0x1800108c1  nop     dword ptr [rax+rax+00h]
0x1800108c6  mov     qword ptr [rbx], 0
0x1800108cd  mov     rbx, [rsp+28h+arg_0]
0x1800108d2  mov     eax, edi
0x1800108d4  add     rsp, 20h
0x1800108d8  pop     rdi
0x1800108d9  retn
```
