# SecpValidateHandle(int,_SecHandle *,_SecHandle *)

- ea: `0x180001f90`
- end: `0x180002047`
- name: `?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z`
- size: `183`
- prototype: `struct _DLL_SECURITY_PACKAGE *__fastcall(int, struct _SecHandle *, struct _SecHandle *)`
- caller_count: `26`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001440`
- `0x1800014e0`
- `0x180001580`
- `0x180001600`
- `0x1800016b0`
- `0x180001730`
- `0x1800017c0`
- `0x180001850`
- `0x1800018f0`
- `0x1800019a0`
- `0x180001a60`
- `0x180001ae0`
- `0x180001b70`
- `0x180001cd0`
- `0x180001d90`
- `0x180001e50`
- `0x180001ef0`
- `0x180003670`
- `0x1800104e0`
- `0x18001a850`
- `0x18001a9b0`
- `0x18001ac70`
- `0x18001ad10`
- `0x18001ae00`
- `0x18001aec0`
- `0x18001af70`

## callees

- `0x180001f90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001fb0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180001fb0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002021`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180002021`

## pseudocode

```c
struct _DLL_SECURITY_PACKAGE *__fastcall SecpValidateHandle(int a1, struct _SecHandle *a2, struct _SecHandle *a3)
{
  ULONG_PTR dwLower; // rdi
  int v7; // ecx

  dwLower = a2->dwLower;
  if ( a2->dwLower - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  if ( (HANDLE)dwLower == GetCurrentThread() )
    dwLower = (ULONG_PTR)TlsGetValue(SecTlsPackage);
  if ( dwLower )
  {
    v7 = *(_DWORD *)(dwLower + 36);
    if ( (v7 & 0x11) != 0 )
    {
      if ( a1 )
      {
        if ( (v7 & 1) != 0 )
        {
          a3->dwLower = *(_QWORD *)(dwLower + 40);
          a3->dwUpper = a2->dwUpper;
          return (struct _DLL_SECURITY_PACKAGE *)dwLower;
        }
      }
      else if ( (v7 & 0x10) != 0 )
      {
        a3->dwLower = *(_QWORD *)(dwLower + 48);
        a3->dwUpper = a2->dwUpper;
        return (struct _DLL_SECURITY_PACKAGE *)dwLower;
      }
    }
    a3->dwLower = a2->dwLower;
    a3->dwUpper = a2->dwUpper;
  }
  return (struct _DLL_SECURITY_PACKAGE *)dwLower;
}

```

## disassembly

```asm
0x180001f90  push    rbx
0x180001f92  push    rsi
0x180001f93  push    rdi
0x180001f94  push    r14
0x180001f96  sub     rsp, 38h
0x180001f9a  mov     rsi, r8
0x180001f9d  mov     rbx, rdx
0x180001fa0  mov     r14d, ecx
0x180001fa3  mov     rdi, [rdx]
0x180001fa6  lea     rax, [rdi-1]
0x180001faa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001fae  ja      short loc_180002012
0x180001fb0  call    cs:__imp_GetCurrentThread
0x180001fb6  cmp     rdi, rax
0x180001fb9  jz      short loc_18000201B
0x180001fbb  mov     [rsp+58h+var_38], rdi
0x180001fc0  test    rdi, rdi
0x180001fc3  jz      short loc_180002031
0x180001fc5  mov     ecx, [rdi+24h]
0x180001fc8  test    cl, 11h
0x180001fcb  jnz     short loc_180001FDD
0x180001fcd  mov     rax, [rbx]
0x180001fd0  mov     [rsi], rax
0x180001fd3  mov     rax, [rbx+8]
0x180001fd7  mov     [rsi+8], rax
0x180001fdb  jmp     short loc_180002031
0x180001fdd  lea     rax, [rdi+24h]
0x180001fe1  test    r14d, r14d
0x180001fe4  jz      short loc_180001FFC
0x180001fe6  test    cl, 1
0x180001fe9  jz      short loc_180001FCD
0x180001feb  mov     rax, [rdi+28h]
0x180001fef  mov     [rsi], rax
0x180001ff2  mov     rax, [rbx+8]
0x180001ff6  mov     [rsi+8], rax
0x180001ffa  jmp     short loc_180002031
0x180001ffc  test    cl, 10h
0x180001fff  jz      short loc_180001FCD
0x180002001  mov     rax, [rdi+30h]
0x180002005  mov     [rsi], rax
0x180002008  mov     rax, [rbx+8]
0x18000200c  mov     [rsi+8], rax
0x180002010  jmp     short loc_180002031
0x180002012  xor     edi, edi
0x180002014  mov     [rsp+58h+var_38], rdi
0x180002019  jmp     short loc_180002031
0x18000201b  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180002021  call    cs:__imp_TlsGetValue
0x180002027  mov     rdi, rax
0x18000202a  mov     [rsp+58h+var_38], rax
0x18000202f  jmp     short loc_180001FC0
0x180002031  jmp     short loc_18000203A
0x180002033  xor     edi, edi
0x180002035  mov     [rsp+58h+var_38], rdi
0x18000203a  mov     rax, rdi
0x18000203d  add     rsp, 38h
0x180002041  pop     r14
0x180002043  pop     rdi
0x180002044  pop     rsi
0x180002045  pop     rbx
0x180002046  retn
```
