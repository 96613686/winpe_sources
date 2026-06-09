# WaitForDirectoryServicesNetworking(ulong)

- ea: `0x180015310`
- end: `0x1800154f1`
- name: `?WaitForDirectoryServicesNetworking@@YAKK@Z`
- size: `481`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180012ff0`
- `0x180013400`
- `0x180014e40`
- `0x180015290`
- `0x180015310`

## import_xrefs

- `msvcrt!clock` at `0x18001532a`
- `msvcrt!clock` at `0x18001534e`
- `msvcrt!clock` at `0x180015482`
- `msvcrt!clock` at `0x18001532a`
- `msvcrt!clock` at `0x18001534e`
- `msvcrt!clock` at `0x180015482`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015425`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015440`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001545a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800154a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800154b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800154ca`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015425`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015440`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001545a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800154a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800154b6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800154ca`
- `KERNEL32!SleepEx` at `0x180015476`
- `KERNEL32!SleepEx` at `0x180015476`

## pseudocode

```c
__int64 __fastcall WaitForDirectoryServicesNetworking(int a1)
{
  unsigned int v2; // esi
  clock_t v3; // eax
  unsigned __int16 *v4; // rbx
  unsigned __int16 *v5; // rdi
  clock_t v6; // r12d
  unsigned int DSInfo; // eax
  unsigned __int16 *v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  _QWORD v12[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v13; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v14; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v15; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 5035;
  v3 = clock();
  v15 = 0;
  v4 = 0;
  v12[0] = 0;
  v5 = 0;
  v6 = v3;
  v13 = 0;
  v14 = 0;
  if ( clock() - v3 < a1 )
  {
    do
    {
      DSInfo = GetDSInfo(0, 0, &v15, 0);
      v8 = v15;
      v2 = DSInfo;
      if ( !DSInfo )
      {
        v2 = CLdap::Open((CLdap *)v12, v15, 0x185u, &stru_18004B618, 0, 0, 0x486u);
        if ( !v2 )
        {
          v9 = QueryDomainInfo(&v13, 0, 0);
          v5 = v13;
          v2 = v9;
          if ( !v9 )
          {
            v10 = GetDSInfo(0, v13, &v14, 0);
            v4 = v14;
            v2 = v10;
            if ( !v10 )
            {
              v2 = CLdap::Open((CLdap *)v12, v14, 0x185u, &stru_18004B618, 0, 0, 0x486u);
              if ( !v2 )
                break;
            }
          }
        }
      }
      if ( v8 )
      {
        operator delete(v8);
        v8 = 0;
        v15 = 0;
      }
      if ( v5 )
      {
        operator delete(v5);
        v5 = 0;
        v13 = 0;
      }
      if ( v4 )
      {
        operator delete(v4);
        v4 = 0;
        v14 = 0;
      }
      SleepEx(0x1388u, 1);
    }
    while ( clock() - v6 < a1 );
    if ( v8 )
      operator delete(v8);
    if ( v5 )
      operator delete(v5);
    if ( v4 )
      operator delete(v4);
  }
  CLdap::Shutdown((CLdap *)v12);
  return v2;
}

```

## disassembly

```asm
0x180015310  push    rbp
0x180015312  push    rbx
0x180015313  push    rsi
0x180015314  push    rdi
0x180015315  push    r12
0x180015317  push    r14
0x180015319  push    r15
0x18001531b  mov     rbp, rsp
0x18001531e  sub     rsp, 50h
0x180015322  mov     r15d, ecx
0x180015325  mov     esi, 13ABh
0x18001532a  call    cs:__imp_clock
0x180015331  nop     dword ptr [rax+rax+00h]
0x180015336  and     [rbp+arg_18], 0
0x18001533b  xor     ebx, ebx
0x18001533d  and     [rbp+var_10], rbx
0x180015341  xor     edi, edi
0x180015343  mov     r12d, eax
0x180015346  mov     [rbp+arg_8], rdi
0x18001534a  mov     [rbp+arg_10], rbx
0x18001534e  call    cs:__imp_clock
0x180015355  nop     dword ptr [rax+rax+00h]
0x18001535a  sub     eax, r12d
0x18001535d  cmp     eax, r15d
0x180015360  jge     loc_1800154D6
0x180015366  xor     r9d, r9d; unsigned __int16 **
0x180015369  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18001536d  xor     edx, edx; unsigned __int16 *
0x18001536f  xor     ecx, ecx; int
0x180015371  call    ?GetDSInfo@@YAKHPEBGPEAPEAG1@Z; GetDSInfo(int,ushort const *,ushort * *,ushort * *)
0x180015376  mov     r14, [rbp+arg_18]
0x18001537a  mov     esi, eax
0x18001537c  test    eax, eax
0x18001537e  jnz     loc_18001541D
0x180015384  mov     [rsp+50h+var_20], 486h; unsigned int
0x18001538c  lea     r9, stru_18004B618; struct l_timeval *
0x180015393  and     [rsp+50h+var_28], 0
0x180015399  lea     rcx, [rbp+var_10]; this
0x18001539d  and     [rsp+50h+var_30], 0
0x1800153a3  mov     r8d, 185h; unsigned int
0x1800153a9  mov     rdx, r14; unsigned __int16 *
0x1800153ac  call    ?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z; CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)
0x1800153b1  mov     esi, eax
0x1800153b3  test    eax, eax
0x1800153b5  jnz     short loc_18001541D
0x1800153b7  xor     r8d, r8d; int *
0x1800153ba  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x1800153be  xor     edx, edx; unsigned __int16 **
0x1800153c0  call    ?QueryDomainInfo@@YAKPEAPEAG0PEAH@Z; QueryDomainInfo(ushort * *,ushort * *,int *)
0x1800153c5  mov     rdi, [rbp+arg_8]
0x1800153c9  mov     esi, eax
0x1800153cb  test    eax, eax
0x1800153cd  jnz     short loc_18001541D
0x1800153cf  xor     r9d, r9d; unsigned __int16 **
0x1800153d2  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x1800153d6  mov     rdx, rdi; unsigned __int16 *
0x1800153d9  xor     ecx, ecx; int
0x1800153db  call    ?GetDSInfo@@YAKHPEBGPEAPEAG1@Z; GetDSInfo(int,ushort const *,ushort * *,ushort * *)
0x1800153e0  mov     rbx, [rbp+arg_10]
0x1800153e4  mov     esi, eax
0x1800153e6  test    eax, eax
0x1800153e8  jnz     short loc_18001541D
0x1800153ea  mov     [rsp+50h+var_20], 486h; unsigned int
0x1800153f2  lea     r9, stru_18004B618; struct l_timeval *
0x1800153f9  and     [rsp+50h+var_28], 0
0x1800153ff  lea     rcx, [rbp+var_10]; this
0x180015403  and     [rsp+50h+var_30], 0
0x180015409  mov     r8d, 185h; unsigned int
0x18001540f  mov     rdx, rbx; unsigned __int16 *
0x180015412  call    ?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z; CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)
0x180015417  mov     esi, eax
0x180015419  test    eax, eax
0x18001541b  jz      short loc_18001549A
0x18001541d  test    r14, r14
0x180015420  jz      short loc_180015438
0x180015422  mov     rcx, r14
0x180015425  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001542c  nop     dword ptr [rax+rax+00h]
0x180015431  xor     r14d, r14d
0x180015434  mov     [rbp+arg_18], r14
0x180015438  test    rdi, rdi
0x18001543b  jz      short loc_180015452
0x18001543d  mov     rcx, rdi
0x180015440  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015447  nop     dword ptr [rax+rax+00h]
0x18001544c  xor     edi, edi
0x18001544e  mov     [rbp+arg_8], rdi
0x180015452  test    rbx, rbx
0x180015455  jz      short loc_18001546C
0x180015457  mov     rcx, rbx
0x18001545a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015461  nop     dword ptr [rax+rax+00h]
0x180015466  xor     ebx, ebx
0x180015468  mov     [rbp+arg_10], rbx
0x18001546c  mov     edx, 1; bAlertable
0x180015471  mov     ecx, 1388h; dwMilliseconds
0x180015476  call    cs:__imp_SleepEx
0x18001547d  nop     dword ptr [rax+rax+00h]
0x180015482  call    cs:__imp_clock
0x180015489  nop     dword ptr [rax+rax+00h]
0x18001548e  sub     eax, r12d
0x180015491  cmp     eax, r15d
0x180015494  jl      loc_180015366
0x18001549a  test    r14, r14
0x18001549d  jz      short loc_1800154AE
0x18001549f  mov     rcx, r14
0x1800154a2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800154a9  nop     dword ptr [rax+rax+00h]
0x1800154ae  test    rdi, rdi
0x1800154b1  jz      short loc_1800154C2
0x1800154b3  mov     rcx, rdi
0x1800154b6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800154bd  nop     dword ptr [rax+rax+00h]
0x1800154c2  test    rbx, rbx
0x1800154c5  jz      short loc_1800154D6
0x1800154c7  mov     rcx, rbx
0x1800154ca  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800154d1  nop     dword ptr [rax+rax+00h]
0x1800154d6  lea     rcx, [rbp+var_10]; this
0x1800154da  call    ?Shutdown@CLdap@@QEAAKXZ; CLdap::Shutdown(void)
0x1800154df  mov     eax, esi
0x1800154e1  add     rsp, 50h
0x1800154e5  pop     r15
0x1800154e7  pop     r14
0x1800154e9  pop     r12
0x1800154eb  pop     rdi
0x1800154ec  pop     rsi
0x1800154ed  pop     rbx
0x1800154ee  pop     rbp
0x1800154ef  retn
```
