# WamRegMetabaseConfig::HasAdminAccess(void)

- ea: `0x180005654`
- end: `0x18000572f`
- name: `?HasAdminAccess@WamRegMetabaseConfig@@QEAAHXZ`
- size: `219`
- prototype: `_BOOL8 __fastcall(WamRegMetabaseConfig *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002460`

## callees

- `0x180005654`
- `0x180007010`

## pseudocode

```c
_BOOL8 __fastcall WamRegMetabaseConfig::HasAdminAccess(WamRegMetabaseConfig *this)
{
  int v1; // ebx
  __int64 v3; // [rsp+40h] [rbp-30h] BYREF
  int v4; // [rsp+48h] [rbp-28h]
  int v5; // [rsp+4Ch] [rbp-24h]
  __int64 v6; // [rsp+50h] [rbp-20h]
  int *v7; // [rsp+58h] [rbp-18h]
  __int64 v8; // [rsp+60h] [rbp-10h]
  unsigned int v9; // [rsp+80h] [rbp+10h] BYREF
  int v10; // [rsp+84h] [rbp+14h]
  int v11; // [rsp+88h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  v9 = 0;
  v1 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, __int64, int, unsigned int *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                                                + 136LL))(
         WamRegMetabaseConfig::m_pMetabase,
         0,
         L"/LM/W3SVC",
         2,
         30000,
         &v9);
  if ( v1 >= 0 )
  {
    v7 = &v11;
    v11 = 4660;
    v6 = 4;
    v8 = 0;
    v3 = 6269;
    v4 = 2;
    v5 = 1;
    v1 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *, __int64 *))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase
                                                                         + 72LL))(
           WamRegMetabaseConfig::m_pMetabase,
           v9,
           &qword_180009278,
           &v3);
    (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)WamRegMetabaseConfig::m_pMetabase + 144LL))(
      WamRegMetabaseConfig::m_pMetabase,
      v9);
  }
  return v1 >= 0;
}

```

## disassembly

```asm
0x180005654  mov     [rsp-8+arg_10], rbx
0x180005659  mov     [rsp-8+arg_0], rcx
0x18000565e  push    rbp
0x18000565f  mov     rbp, rsp
0x180005662  sub     rsp, 70h
0x180005666  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x18000566d  lea     rdx, [rbp+arg_0]
0x180005671  mov     [rsp+70h+var_48], rdx
0x180005676  lea     r8, ?g_szMDW3SVCRoot@WamRegGlobal@@2QBGB; "/LM/W3SVC"
0x18000567d  mov     dword ptr [rbp+arg_0], 0
0x180005684  mov     r9d, 2
0x18000568a  xor     edx, edx
0x18000568c  mov     [rsp+70h+var_50], 7530h
0x180005694  mov     rax, [rcx]
0x180005697  mov     rax, [rax+88h]
0x18000569e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a3  mov     ebx, eax
0x1800056a5  test    eax, eax
0x1800056a7  js      short loc_18000571A
0x1800056a9  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x1800056b0  lea     rax, [rbp+arg_8]
0x1800056b4  mov     edx, dword ptr [rbp+arg_0]
0x1800056b7  lea     r9, [rbp+var_30]
0x1800056bb  mov     [rbp+var_18], rax
0x1800056bf  lea     r8, qword_180009278
0x1800056c6  mov     [rbp+arg_8], 1234h
0x1800056cd  mov     [rbp+var_20], 4
0x1800056d5  mov     [rbp+var_10], 0
0x1800056dd  mov     [rbp+var_30], 187Dh
0x1800056e5  mov     [rbp+var_28], 2
0x1800056ec  mov     [rbp+var_24], 1
0x1800056f3  mov     rax, [rcx]
0x1800056f6  mov     rax, [rax+48h]
0x1800056fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ff  mov     rcx, cs:?m_pMetabase@WamRegMetabaseConfig@@0PEAUIMSAdminBaseW@@EA; IMSAdminBaseW * WamRegMetabaseConfig::m_pMetabase
0x180005706  mov     ebx, eax
0x180005708  mov     edx, dword ptr [rbp+arg_0]
0x18000570b  mov     rax, [rcx]
0x18000570e  mov     rax, [rax+90h]
0x180005715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571a  not     ebx
0x18000571c  shr     ebx, 1Fh
0x18000571f  mov     eax, ebx
0x180005721  mov     rbx, [rsp+70h+arg_10]
0x180005729  add     rsp, 70h
0x18000572d  pop     rbp
0x18000572e  retn
```
