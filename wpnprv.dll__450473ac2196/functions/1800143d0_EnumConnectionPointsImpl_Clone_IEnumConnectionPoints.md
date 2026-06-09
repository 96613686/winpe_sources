# EnumConnectionPointsImpl::Clone(IEnumConnectionPoints * *)

- ea: `0x1800143d0`
- end: `0x1800145a6`
- name: `?Clone@EnumConnectionPointsImpl@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(EnumConnectionPointsImpl *this, struct IEnumConnectionPoints **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000795c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x180014248`
- `0x1800143d0`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800144eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800144eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800144c2`

## string_xrefs

- `0x180014457`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\enumconnectionpointsimpl.cpp`
- `0x18001452c`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\enumconnectionpointsimpl.cpp`

## pseudocode

```c
__int64 __fastcall EnumConnectionPointsImpl::Clone(EnumConnectionPointsImpl *this, struct IEnumConnectionPoints **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // edi
  PVOID *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  EnumConnectionPointsImpl *v9; // rax
  EnumConnectionPointsImpl *v10; // rbp
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_072d72f3783e3781814a63546cd35d1e_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v9 = (EnumConnectionPointsImpl *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v9 )
    {
      v10 = EnumConnectionPointsImpl::EnumConnectionPointsImpl(v9);
      if ( v10 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        *((_QWORD *)v10 + 6) = *((_QWORD *)this + 6);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
        *((_BYTE *)v10 + 56) = *((_BYTE *)this + 56);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        *a2 = (struct IEnumConnectionPoints *)v10;
LABEL_24:
        v6 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_25;
      }
    }
    v5 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_072d72f3783e3781814a63546cd35d1e_Traceguids, 2147942414LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x107,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\enumconnectionpointsimpl.cpp",
      (const char *)0x8007000ELL);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v7 = 26;
        v8 = 2147942414LL;
        goto LABEL_23;
      }
LABEL_25:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 6u )
        WPP_SF_d(v6[2], 27, WPP_072d72f3783e3781814a63546cd35d1e_Traceguids, v5);
    }
  }
  else
  {
    v5 = -2147024809;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_d(v4[2], 23, WPP_072d72f3783e3781814a63546cd35d1e_Traceguids, 2147942487LL);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFD,
      (int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\enumconnectionpointsimpl.cpp",
      (const char *)0x80070057LL);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v7 = 24;
        v8 = 2147942487LL;
LABEL_23:
        WPP_SF_d(v6[2], v7, WPP_072d72f3783e3781814a63546cd35d1e_Traceguids, v8);
        goto LABEL_24;
      }
      goto LABEL_25;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800143d0  push    rbx
0x1800143d2  push    rbp
0x1800143d3  push    rsi
0x1800143d4  push    rdi
0x1800143d5  push    r12
0x1800143d7  push    r14
0x1800143d9  push    r15; int
0x1800143db  sub     rsp, 20h
0x1800143df  mov     rsi, rdx
0x1800143e2  mov     r14, rcx
0x1800143e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800143ec  lea     r15, WPP_GLOBAL_Control
0x1800143f3  lea     r12, WPP_072d72f3783e3781814a63546cd35d1e_Traceguids
0x1800143fa  cmp     rcx, r15
0x1800143fd  jz      short loc_180014423
0x1800143ff  test    byte ptr [rcx+1Ch], 1
0x180014403  jz      short loc_180014423
0x180014405  cmp     byte ptr [rcx+19h], 6
0x180014409  jb      short loc_180014423
0x18001440b  mov     rcx, [rcx+10h]
0x18001440f  mov     edx, 16h
0x180014414  mov     r8, r12
0x180014417  call    WPP_SF_
0x18001441c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014423  xor     edi, edi
0x180014425  test    rsi, rsi
0x180014428  jnz     short loc_180014495
0x18001442a  mov     edi, 80070057h
0x18001442f  cmp     rcx, r15
0x180014432  jz      short loc_180014452
0x180014434  test    byte ptr [rcx+1Ch], 1
0x180014438  jz      short loc_180014452
0x18001443a  cmp     byte ptr [rcx+19h], 2
0x18001443e  jb      short loc_180014452
0x180014440  mov     rcx, [rcx+10h]
0x180014444  lea     edx, [rsi+17h]
0x180014447  mov     r9d, edi
0x18001444a  mov     r8, r12
0x18001444d  call    WPP_SF_d
0x180014452  mov     rcx, [rsp+58h]; this
0x180014457  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001445e  mov     r9d, edi; char *
0x180014461  mov     edx, 0FDh; void *
0x180014466  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001446b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014472  cmp     rcx, r15
0x180014475  jz      loc_180014595
0x18001447b  test    byte ptr [rcx+1Ch], 80h
0x18001447f  jz      loc_180014570
0x180014485  mov     edx, 18h
0x18001448a  mov     r9d, 80070057h
0x180014490  jmp     loc_18001455D
0x180014495  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001449c  mov     [rsi], rdi
0x18001449f  mov     ecx, 40h ; '@'; unsigned __int64
0x1800144a4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800144a9  test    rax, rax
0x1800144ac  jz      short loc_1800144F6
0x1800144ae  mov     rcx, rax; this
0x1800144b1  call    ??0EnumConnectionPointsImpl@@AEAA@XZ; EnumConnectionPointsImpl::EnumConnectionPointsImpl(void)
0x1800144b6  mov     rbp, rax
0x1800144b9  test    rax, rax
0x1800144bc  jz      short loc_1800144F6
0x1800144be  lea     rcx, [r14+8]; lpCriticalSection
0x1800144c2  call    cs:__imp_EnterCriticalSection
0x1800144c8  mov     rax, [r14+30h]
0x1800144cc  mov     [rbp+30h], rax
0x1800144d0  mov     rcx, [r14+30h]
0x1800144d4  mov     rax, [rcx]
0x1800144d7  mov     rax, [rax+8]
0x1800144db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144e0  mov     al, [r14+38h]
0x1800144e4  lea     rcx, [r14+8]; lpCriticalSection
0x1800144e8  mov     [rbp+38h], al
0x1800144eb  call    cs:__imp_LeaveCriticalSection
0x1800144f1  mov     [rsi], rbp
0x1800144f4  jmp     short loc_180014569
0x1800144f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144fd  mov     edi, 8007000Eh
0x180014502  cmp     rcx, r15
0x180014505  jz      short loc_180014527
0x180014507  test    byte ptr [rcx+1Ch], 1
0x18001450b  jz      short loc_180014527
0x18001450d  cmp     byte ptr [rcx+19h], 2
0x180014511  jb      short loc_180014527
0x180014513  mov     rcx, [rcx+10h]
0x180014517  mov     edx, 19h
0x18001451c  mov     r9d, edi
0x18001451f  mov     r8, r12
0x180014522  call    WPP_SF_d
0x180014527  mov     rcx, [rsp+58h]; this
0x18001452c  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180014533  mov     r9d, edi; char *
0x180014536  mov     edx, 107h; void *
0x18001453b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014540  mov     rcx, cs:WPP_GLOBAL_Control
0x180014547  cmp     rcx, r15
0x18001454a  jz      short loc_180014595
0x18001454c  test    byte ptr [rcx+1Ch], 80h
0x180014550  jz      short loc_180014570
0x180014552  mov     edx, 1Ah
0x180014557  mov     r9d, 8007000Eh
0x18001455d  mov     rcx, [rcx+10h]
0x180014561  mov     r8, r12
0x180014564  call    WPP_SF_d
0x180014569  mov     rcx, cs:WPP_GLOBAL_Control
0x180014570  cmp     rcx, r15
0x180014573  jz      short loc_180014595
0x180014575  test    byte ptr [rcx+1Ch], 1
0x180014579  jz      short loc_180014595
0x18001457b  cmp     byte ptr [rcx+19h], 6
0x18001457f  jb      short loc_180014595
0x180014581  mov     rcx, [rcx+10h]
0x180014585  mov     edx, 1Bh
0x18001458a  mov     r9d, edi
0x18001458d  mov     r8, r12
0x180014590  call    WPP_SF_d
0x180014595  mov     eax, edi
0x180014597  add     rsp, 20h
0x18001459b  pop     r15
0x18001459d  pop     r14
0x18001459f  pop     r12
0x1800145a1  pop     rdi
0x1800145a2  pop     rsi
0x1800145a3  pop     rbp
0x1800145a4  pop     rbx
0x1800145a5  retn
```
