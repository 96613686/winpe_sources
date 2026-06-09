# WaitForDirectoryServicesNetworking(ulong)

- ea: `0x180014640`
- end: `0x1800147f7`
- name: `?WaitForDirectoryServicesNetworking@@YAKK@Z`
- size: `439`
- prototype: `unsigned int __fastcall(unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x1800123b0`
- `0x1800127a0`
- `0x180014170`
- `0x1800145c0`
- `0x180014640`
- `0x18002e468`

## import_xrefs

- `msvcrt!clock` at `0x18001465a`
- `msvcrt!clock` at `0x18001467e`
- `msvcrt!clock` at `0x18001479d`
- `msvcrt!clock` at `0x18001465a`
- `msvcrt!clock` at `0x18001467e`
- `msvcrt!clock` at `0x18001479d`
- `KERNEL32!SleepEx` at `0x180014791`
- `KERNEL32!SleepEx` at `0x180014791`

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
  void *v8; // r14
  unsigned int v9; // eax
  unsigned int v10; // eax
  _QWORD v12[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v13; // [rsp+98h] [rbp+48h] BYREF
  unsigned __int16 *v14; // [rsp+A0h] [rbp+50h] BYREF
  void *lpMem; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 5035;
  v3 = clock();
  lpMem = 0;
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
      DSInfo = GetDSInfo(0, 0, (unsigned __int16 **)&lpMem, 0);
      v8 = lpMem;
      v2 = DSInfo;
      if ( !DSInfo )
      {
        v2 = CLdap::Open((CLdap *)v12, (const unsigned __int16 *)lpMem, 0x185u, &stru_180049558, 0, 0, 0x486u);
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
              v2 = CLdap::Open((CLdap *)v12, v14, 0x185u, &stru_180049558, 0, 0, 0x486u);
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
        lpMem = 0;
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
0x180014640  push    rbp
0x180014642  push    rbx
0x180014643  push    rsi
0x180014644  push    rdi
0x180014645  push    r12
0x180014647  push    r14
0x180014649  push    r15
0x18001464b  mov     rbp, rsp
0x18001464e  sub     rsp, 50h
0x180014652  mov     r15d, ecx
0x180014655  mov     esi, 13ABh
0x18001465a  call    cs:__imp_clock
0x180014661  nop     dword ptr [rax+rax+00h]
0x180014666  and     [rbp+lpMem], 0
0x18001466b  xor     ebx, ebx
0x18001466d  and     [rbp+var_10], rbx
0x180014671  xor     edi, edi
0x180014673  mov     r12d, eax
0x180014676  mov     [rbp+arg_8], rdi
0x18001467a  mov     [rbp+arg_10], rbx
0x18001467e  call    cs:__imp_clock
0x180014685  nop     dword ptr [rax+rax+00h]
0x18001468a  sub     eax, r12d
0x18001468d  cmp     eax, r15d
0x180014690  jge     loc_1800147DC
0x180014696  xor     r9d, r9d; unsigned __int16 **
0x180014699  lea     r8, [rbp+lpMem]; unsigned __int16 **
0x18001469d  xor     edx, edx; unsigned __int16 *
0x18001469f  xor     ecx, ecx; int
0x1800146a1  call    ?GetDSInfo@@YAKHPEBGPEAPEAG1@Z; GetDSInfo(int,ushort const *,ushort * *,ushort * *)
0x1800146a6  mov     r14, [rbp+lpMem]
0x1800146aa  mov     esi, eax
0x1800146ac  test    eax, eax
0x1800146ae  jnz     loc_18001474D
0x1800146b4  mov     [rsp+50h+var_20], 486h; unsigned int
0x1800146bc  lea     r9, stru_180049558; struct l_timeval *
0x1800146c3  and     [rsp+50h+var_28], 0
0x1800146c9  lea     rcx, [rbp+var_10]; this
0x1800146cd  and     [rsp+50h+var_30], 0
0x1800146d3  mov     r8d, 185h; unsigned int
0x1800146d9  mov     rdx, r14; unsigned __int16 *
0x1800146dc  call    ?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z; CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)
0x1800146e1  mov     esi, eax
0x1800146e3  test    eax, eax
0x1800146e5  jnz     short loc_18001474D
0x1800146e7  xor     r8d, r8d; int *
0x1800146ea  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x1800146ee  xor     edx, edx; unsigned __int16 **
0x1800146f0  call    ?QueryDomainInfo@@YAKPEAPEAG0PEAH@Z; QueryDomainInfo(ushort * *,ushort * *,int *)
0x1800146f5  mov     rdi, [rbp+arg_8]
0x1800146f9  mov     esi, eax
0x1800146fb  test    eax, eax
0x1800146fd  jnz     short loc_18001474D
0x1800146ff  xor     r9d, r9d; unsigned __int16 **
0x180014702  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x180014706  mov     rdx, rdi; unsigned __int16 *
0x180014709  xor     ecx, ecx; int
0x18001470b  call    ?GetDSInfo@@YAKHPEBGPEAPEAG1@Z; GetDSInfo(int,ushort const *,ushort * *,ushort * *)
0x180014710  mov     rbx, [rbp+arg_10]
0x180014714  mov     esi, eax
0x180014716  test    eax, eax
0x180014718  jnz     short loc_18001474D
0x18001471a  mov     [rsp+50h+var_20], 486h; unsigned int
0x180014722  lea     r9, stru_180049558; struct l_timeval *
0x180014729  and     [rsp+50h+var_28], 0
0x18001472f  lea     rcx, [rbp+var_10]; this
0x180014733  and     [rsp+50h+var_30], 0
0x180014739  mov     r8d, 185h; unsigned int
0x18001473f  mov     rdx, rbx; unsigned __int16 *
0x180014742  call    ?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z; CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)
0x180014747  mov     esi, eax
0x180014749  test    eax, eax
0x18001474b  jz      short loc_1800147B5
0x18001474d  test    r14, r14
0x180014750  jz      short loc_180014761
0x180014752  mov     rcx, r14; lpMem
0x180014755  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001475a  xor     r14d, r14d
0x18001475d  mov     [rbp+lpMem], r14
0x180014761  test    rdi, rdi
0x180014764  jz      short loc_180014774
0x180014766  mov     rcx, rdi; lpMem
0x180014769  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001476e  xor     edi, edi
0x180014770  mov     [rbp+arg_8], rdi
0x180014774  test    rbx, rbx
0x180014777  jz      short loc_180014787
0x180014779  mov     rcx, rbx; lpMem
0x18001477c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014781  xor     ebx, ebx
0x180014783  mov     [rbp+arg_10], rbx
0x180014787  mov     edx, 1; bAlertable
0x18001478c  mov     ecx, 1388h; dwMilliseconds
0x180014791  call    cs:__imp_SleepEx
0x180014798  nop     dword ptr [rax+rax+00h]
0x18001479d  call    cs:__imp_clock
0x1800147a4  nop     dword ptr [rax+rax+00h]
0x1800147a9  sub     eax, r12d
0x1800147ac  cmp     eax, r15d
0x1800147af  jl      loc_180014696
0x1800147b5  test    r14, r14
0x1800147b8  jz      short loc_1800147C2
0x1800147ba  mov     rcx, r14; lpMem
0x1800147bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800147c2  test    rdi, rdi
0x1800147c5  jz      short loc_1800147CF
0x1800147c7  mov     rcx, rdi; lpMem
0x1800147ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800147cf  test    rbx, rbx
0x1800147d2  jz      short loc_1800147DC
0x1800147d4  mov     rcx, rbx; lpMem
0x1800147d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800147dc  lea     rcx, [rbp+var_10]; this
0x1800147e0  call    ?Shutdown@CLdap@@QEAAKXZ; CLdap::Shutdown(void)
0x1800147e5  mov     eax, esi
0x1800147e7  add     rsp, 50h
0x1800147eb  pop     r15
0x1800147ed  pop     r14
0x1800147ef  pop     r12
0x1800147f1  pop     rdi
0x1800147f2  pop     rsi
0x1800147f3  pop     rbx
0x1800147f4  pop     rbp
0x1800147f5  retn
```
