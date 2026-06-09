# CSGetGroupAccountInfoByRID

- ea: `0x1800123c0`
- end: `0x1800125e2`
- name: `CSGetGroupAccountInfoByRID`
- size: `546`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, HDPA)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002ff0`

## callees

- `0x180003660`
- `0x180009190`
- `0x18000cb84`
- `0x180011e80`
- `0x1800123c0`
- `0x180013534`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001256c`
- `ntdll!RtlInitUnicodeString` at `0x18001256c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800124d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012592`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012494`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012494`
- `SAMLIB!SamCloseHandle` at `0x18001254a`
- `SAMLIB!SamCloseHandle` at `0x180012554`
- `SAMLIB!SamCloseHandle` at `0x18001254a`
- `SAMLIB!SamCloseHandle` at `0x180012554`
- `SAMLIB!SamLookupIdsInDomain` at `0x18001245a`
- `SAMLIB!SamLookupIdsInDomain` at `0x18001245a`
- `SAMLIB!SamFreeMemory` at `0x1800124f3`
- `SAMLIB!SamFreeMemory` at `0x1800124fd`
- `SAMLIB!SamFreeMemory` at `0x1800124f3`
- `SAMLIB!SamFreeMemory` at `0x1800124fd`

## pseudocode

```c
__int64 __fastcall CSGetGroupAccountInfoByRID(
        void *a1,
        unsigned int a2,
        struct _UNICODE_STRING **a3,
        struct _ALIAS_EXTENDED_INFORMATION **a4,
        HDPA hdpa)
{
  void *v8; // rdi
  int v9; // ebx
  WCHAR *v10; // rsi
  int v11; // ebx
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rdi
  _DWORD *v16; // [rsp+30h] [rbp-20h] BYREF
  void *v17; // [rsp+38h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+50h] BYREF
  const unsigned __int16 **v21; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = 0;
  *a4 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v17 = 0;
  v8 = a1;
  v9 = SamHandleForDomain(a1, 0x20021u, 0x20385u, (void **)&DestinationString, &v17);
  if ( v9 < 0 )
    goto LABEL_21;
  v10 = 0;
  v20 = a2;
  v21 = 0;
  v16 = 0;
  v11 = SamLookupIdsInDomain(v17, 1, &v20, &v21, &v16);
  if ( v11 < 0 )
  {
    if ( v11 == -1073741709 )
    {
      v9 = -2147023728;
    }
    else
    {
      v9 = v11 | 0x10000000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, a2, v9);
    }
  }
  else
  {
    if ( *v16 == 4 || *v16 == 1 )
    {
      v12 = ((unsigned __int64)*(unsigned __int16 *)v21 + 2) >> 1;
      v13 = (unsigned __int16 *)CoTaskMemAlloc(2 * v12);
      v14 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, 2 * v12);
        v9 = StringCchCopyNW(v14, v12, v21[1], (unsigned __int64)*(unsigned __int16 *)v21 >> 1);
        if ( v9 >= 0 )
          v10 = v14;
        else
          CoTaskMemFree(v14);
      }
      else
      {
        v9 = -2147024882;
      }
      v8 = a1;
    }
    else
    {
      v9 = -805306230;
    }
    SamFreeMemory(v16);
    SamFreeMemory(v21);
  }
  SamCloseHandle(v17);
  SamCloseHandle(*(_QWORD *)&DestinationString.Length);
  if ( v9 < 0 )
  {
LABEL_21:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, a2, v9);
  }
  else
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v10);
    v9 = CSGetGroupAccountInfo(v8, (__int64)&DestinationString, a3, a4, hdpa);
    CoTaskMemFree(v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800123c0  mov     [rsp-38h+arg_8], rbx
0x1800123c5  mov     [rsp-38h+arg_0], rcx
0x1800123ca  push    rbp
0x1800123cb  push    rsi
0x1800123cc  push    rdi
0x1800123cd  push    r12
0x1800123cf  push    r13
0x1800123d1  push    r14
0x1800123d3  push    r15
0x1800123d5  mov     rbp, rsp
0x1800123d8  sub     rsp, 50h
0x1800123dc  mov     qword ptr [r8], 0
0x1800123e3  lea     rax, [rbp+var_18]
0x1800123e7  mov     qword ptr [r9], 0
0x1800123ee  mov     r12, r9
0x1800123f1  mov     r13, r8
0x1800123f4  mov     qword ptr [rbp+DestinationString.Length], 0
0x1800123fc  mov     r14d, edx
0x1800123ff  mov     [rbp+var_18], 0
0x180012407  lea     r9, [rbp+DestinationString]; void **
0x18001240b  mov     [rsp+50h+hdpa], rax; void **
0x180012410  mov     edx, 20021h; unsigned int
0x180012415  mov     r8d, 20385h; unsigned int
0x18001241b  mov     rdi, rcx
0x18001241e  call    ?SamHandleForDomain@@YAJPEAXKKPEAPEAX1@Z; SamHandleForDomain(void *,ulong,ulong,void * *,void * *)
0x180012423  lea     r15, WPP_GLOBAL_Control
0x18001242a  mov     ebx, eax
0x18001242c  test    eax, eax
0x18001242e  js      loc_18001259A
0x180012434  mov     rcx, [rbp+var_18]
0x180012438  lea     rax, [rbp+var_20]
0x18001243c  xor     esi, esi
0x18001243e  mov     [rbp+arg_10], r14d
0x180012442  lea     r9, [rbp+arg_18]
0x180012446  mov     [rbp+arg_18], rsi
0x18001244a  lea     r8, [rbp+arg_10]
0x18001244e  mov     [rbp+var_20], rsi
0x180012452  mov     [rsp+50h+hdpa], rax
0x180012457  lea     edx, [rsi+1]
0x18001245a  call    cs:__imp_SamLookupIdsInDomain
0x180012460  mov     ebx, eax
0x180012462  test    eax, eax
0x180012464  js      loc_180012505
0x18001246a  mov     rax, [rbp+var_20]
0x18001246e  cmp     dword ptr [rax], 4
0x180012471  jz      short loc_18001247F
0x180012473  cmp     dword ptr [rax], 1
0x180012476  jz      short loc_18001247F
0x180012478  mov     ebx, 0D000008Ah
0x18001247d  jmp     short loc_1800124EF
0x18001247f  mov     rax, [rbp+arg_18]
0x180012483  movzx   ebx, word ptr [rax]
0x180012486  add     rbx, 2
0x18001248a  shr     rbx, 1
0x18001248d  lea     r15, [rbx+rbx]
0x180012491  mov     rcx, r15; cb
0x180012494  call    cs:__imp_CoTaskMemAlloc
0x18001249a  mov     rdi, rax
0x18001249d  test    rax, rax
0x1800124a0  jnz     short loc_1800124A9
0x1800124a2  mov     ebx, 8007000Eh
0x1800124a7  jmp     short loc_1800124E4
0x1800124a9  mov     r8, r15; Size
0x1800124ac  xor     edx, edx; Val
0x1800124ae  mov     rcx, rdi; void *
0x1800124b1  call    memset_0
0x1800124b6  mov     r8, [rbp+arg_18]
0x1800124ba  mov     rdx, rbx; unsigned __int64
0x1800124bd  mov     rcx, rdi; unsigned __int16 *
0x1800124c0  movzx   r9d, word ptr [r8]
0x1800124c4  mov     r8, [r8+8]; unsigned __int16 *
0x1800124c8  shr     r9, 1; unsigned __int64
0x1800124cb  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800124d0  mov     ebx, eax
0x1800124d2  test    eax, eax
0x1800124d4  jns     short loc_1800124E1
0x1800124d6  mov     rcx, rdi; pv
0x1800124d9  call    cs:__imp_CoTaskMemFree
0x1800124df  jmp     short loc_1800124E4
0x1800124e1  mov     rsi, rdi
0x1800124e4  mov     rdi, [rbp+arg_0]
0x1800124e8  lea     r15, WPP_GLOBAL_Control
0x1800124ef  mov     rcx, [rbp+var_20]
0x1800124f3  call    cs:__imp_SamFreeMemory
0x1800124f9  mov     rcx, [rbp+arg_18]
0x1800124fd  call    cs:__imp_SamFreeMemory
0x180012503  jmp     short loc_180012546
0x180012505  cmp     ebx, 0C0000073h
0x18001250b  jnz     short loc_180012514
0x18001250d  mov     ebx, 80070490h
0x180012512  jmp     short loc_180012546
0x180012514  bts     ebx, 1Ch
0x180012518  mov     rcx, cs:WPP_GLOBAL_Control
0x18001251f  cmp     rcx, r15
0x180012522  jz      short loc_180012546
0x180012524  test    byte ptr [rcx+1Ch], 2
0x180012528  jz      short loc_180012546
0x18001252a  mov     rcx, [rcx+10h]
0x18001252e  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180012535  mov     edx, 43h ; 'C'
0x18001253a  mov     dword ptr [rsp+50h+hdpa], ebx
0x18001253e  mov     r9d, r14d
0x180012541  call    WPP_SF_dD
0x180012546  mov     rcx, [rbp+var_18]
0x18001254a  call    cs:__imp_SamCloseHandle
0x180012550  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x180012554  call    cs:__imp_SamCloseHandle
0x18001255a  test    ebx, ebx
0x18001255c  js      short loc_18001259A
0x18001255e  xorps   xmm0, xmm0
0x180012561  lea     rcx, [rbp+DestinationString]; DestinationString
0x180012565  mov     rdx, rsi; SourceString
0x180012568  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001256c  call    cs:__imp_RtlInitUnicodeString
0x180012572  mov     rax, [rbp+arg_20]
0x180012576  lea     rdx, [rbp+DestinationString]; int
0x18001257a  mov     r9, r12; int
0x18001257d  mov     [rsp+50h+hdpa], rax; hdpa
0x180012582  mov     r8, r13; int
0x180012585  mov     rcx, rdi; int
0x180012588  call    CSGetGroupAccountInfo
0x18001258d  mov     rcx, rsi; pv
0x180012590  mov     ebx, eax
0x180012592  call    cs:__imp_CoTaskMemFree
0x180012598  jmp     short loc_1800125C8
0x18001259a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125a1  cmp     rcx, r15
0x1800125a4  jz      short loc_1800125C8
0x1800125a6  test    byte ptr [rcx+1Ch], 4
0x1800125aa  jz      short loc_1800125C8
0x1800125ac  mov     rcx, [rcx+10h]
0x1800125b0  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800125b7  mov     edx, 41h ; 'A'
0x1800125bc  mov     dword ptr [rsp+50h+hdpa], ebx
0x1800125c0  mov     r9d, r14d
0x1800125c3  call    WPP_SF_dD
0x1800125c8  mov     eax, ebx
0x1800125ca  mov     rbx, [rsp+50h+arg_8]
0x1800125d2  add     rsp, 50h
0x1800125d6  pop     r15
0x1800125d8  pop     r14
0x1800125da  pop     r13
0x1800125dc  pop     r12
0x1800125de  pop     rdi
0x1800125df  pop     rsi
0x1800125e0  pop     rbp
0x1800125e1  retn
```
