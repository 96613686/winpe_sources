# FindLatestExpiredAM(__MIDL_SecurityCenter_0001 *,ulong,ulong *)

- ea: `0x18000a3e8`
- end: `0x18000a4fa`
- name: `?FindLatestExpiredAM@@YAJPEAU__MIDL_SecurityCenter_0001@@KPEAK@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct __MIDL_SecurityCenter_0001 *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009dfc`

## callees

- `0x180008170`
- `0x1800081c4`
- `0x18000a3e8`
- `0x18000a640`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x18000a486`
- `KERNEL32!SystemTimeToFileTime` at `0x18000a486`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x18000a476`
- `WINHTTP!WinHttpTimeToSystemTime` at `0x18000a476`

## pseudocode

```c
__int64 __fastcall FindLatestExpiredAM(struct __MIDL_SecurityCenter_0001 *a1, unsigned int a2, unsigned int *a3)
{
  int v3; // ebx
  struct _FILETIME v4; // r13
  unsigned int v5; // edi
  __int64 v8; // rsi
  unsigned int v9; // r15d
  const WCHAR *v10; // rcx
  struct _FILETIME FileTime; // [rsp+20h] [rbp-78h] BYREF
  struct _FILETIME v13; // [rsp+28h] [rbp-70h]
  struct _FILETIME v14; // [rsp+30h] [rbp-68h]
  unsigned int *v15; // [rsp+38h] [rbp-60h]
  SYSTEMTIME pst; // [rsp+40h] [rbp-58h] BYREF

  v3 = 0;
  v15 = a3;
  v4 = 0;
  FileTime = 0;
  v5 = 0;
  pst = 0;
  if ( a2 )
  {
    v8 = 0;
    do
    {
      v9 = *((_DWORD *)a1 + 20 * v8);
      if ( ((unsigned int)ExtractProductOwner(v9) == 256 || (v9 & 0x40000) != 0)
        && (unsigned int)ExtractProductState(*((unsigned int *)a1 + 20 * v8)) == 0x4000 )
      {
        v10 = (const WCHAR *)*((_QWORD *)a1 + 10 * v8 + 3);
        if ( v10 )
        {
          WinHttpTimeToSystemTime(v10, &pst);
          SystemTimeToFileTime(&pst, &FileTime);
          v13 = FileTime;
          if ( *(_QWORD *)&FileTime > *(unsigned __int64 *)&v4 )
          {
            v14 = FileTime;
            v3 = 1;
            v4 = FileTime;
            *v15 = v5;
          }
        }
      }
      ++v5;
      ++v8;
    }
    while ( v5 < a2 );
  }
  return v3 == 0 ? 0x80070002 : 0;
}

```

## disassembly

```asm
0x18000a3e8  mov     [rsp+arg_8], rbx
0x18000a3ed  push    rbp
0x18000a3ee  push    rsi
0x18000a3ef  push    rdi
0x18000a3f0  push    r12
0x18000a3f2  push    r13
0x18000a3f4  push    r14
0x18000a3f6  push    r15
0x18000a3f8  sub     rsp, 60h
0x18000a3fc  mov     rax, cs:__security_cookie
0x18000a403  xor     rax, rsp
0x18000a406  mov     [rsp+98h+var_48], rax
0x18000a40b  xor     ebx, ebx
0x18000a40d  mov     [rsp+98h+var_60], r8
0x18000a412  xor     r13d, r13d
0x18000a415  mov     qword ptr [rsp+98h+FileTime.dwLowDateTime], rbx
0x18000a41a  xor     edi, edi
0x18000a41c  xorps   xmm0, xmm0
0x18000a41f  mov     r12d, edx
0x18000a422  mov     rbp, rcx
0x18000a425  movups  xmmword ptr [rsp+98h+pst.wYear], xmm0
0x18000a42a  test    edx, edx
0x18000a42c  jz      loc_18000A4CA
0x18000a432  xor     esi, esi
0x18000a434  lea     r14, [rsi+rsi*4]
0x18000a438  add     r14, r14
0x18000a43b  mov     r15d, [rbp+r14*8+0]
0x18000a440  mov     ecx, r15d
0x18000a443  call    ?ExtractProductOwner@@YA?AW4ProductOwner@@K@Z; ExtractProductOwner(ulong)
0x18000a448  cmp     eax, 100h
0x18000a44d  jz      short loc_18000A456
0x18000a44f  bt      r15d, 12h
0x18000a454  jnb     short loc_18000A4BC
0x18000a456  mov     ecx, [rbp+r14*8+0]
0x18000a45b  call    ?ExtractProductState@@YA?AW4ProductState@@K@Z; ExtractProductState(ulong)
0x18000a460  cmp     eax, 4000h
0x18000a465  jnz     short loc_18000A4BC
0x18000a467  mov     rcx, [rbp+r14*8+18h]; pwszTime
0x18000a46c  test    rcx, rcx
0x18000a46f  jz      short loc_18000A4BC
0x18000a471  lea     rdx, [rsp+98h+pst]; pst
0x18000a476  call    cs:__imp_WinHttpTimeToSystemTime
0x18000a47c  lea     rdx, [rsp+98h+FileTime]; lpFileTime
0x18000a481  lea     rcx, [rsp+98h+pst]; lpSystemTime
0x18000a486  call    cs:__imp_SystemTimeToFileTime
0x18000a48c  mov     eax, [rsp+98h+FileTime.dwLowDateTime]
0x18000a490  mov     ecx, [rsp+98h+FileTime.dwHighDateTime]
0x18000a494  mov     dword ptr [rsp+98h+var_70], eax
0x18000a498  mov     dword ptr [rsp+98h+var_70+4], ecx
0x18000a49c  cmp     [rsp+98h+var_70], r13
0x18000a4a1  jbe     short loc_18000A4BC
0x18000a4a3  mov     dword ptr [rsp+98h+var_68], eax
0x18000a4a7  mov     ebx, 1
0x18000a4ac  mov     rax, [rsp+98h+var_60]
0x18000a4b1  mov     dword ptr [rsp+98h+var_68+4], ecx
0x18000a4b5  mov     r13, [rsp+98h+var_68]
0x18000a4ba  mov     [rax], edi
0x18000a4bc  inc     edi
0x18000a4be  inc     rsi
0x18000a4c1  cmp     edi, r12d
0x18000a4c4  jb      loc_18000A434
0x18000a4ca  neg     ebx
0x18000a4cc  sbb     eax, eax
0x18000a4ce  not     eax
0x18000a4d0  and     eax, 80070002h
0x18000a4d5  mov     rcx, [rsp+98h+var_48]
0x18000a4da  xor     rcx, rsp; StackCookie
0x18000a4dd  call    __security_check_cookie
0x18000a4e2  mov     rbx, [rsp+98h+arg_8]
0x18000a4ea  add     rsp, 60h
0x18000a4ee  pop     r15
0x18000a4f0  pop     r14
0x18000a4f2  pop     r13
0x18000a4f4  pop     r12
0x18000a4f6  pop     rdi
0x18000a4f7  pop     rsi
0x18000a4f8  pop     rbp
0x18000a4f9  retn
```
