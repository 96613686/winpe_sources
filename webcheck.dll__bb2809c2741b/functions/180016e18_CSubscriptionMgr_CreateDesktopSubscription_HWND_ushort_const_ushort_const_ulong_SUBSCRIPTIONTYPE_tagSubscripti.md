# CSubscriptionMgr::CreateDesktopSubscription(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)

- ea: `0x180016e18`
- end: `0x180016f79`
- name: `?CreateDesktopSubscription@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z`
- size: `353`
- prototype: `__int64 __fastcall(CSubscriptionMgr *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, unsigned int, enum SUBSCRIPTIONTYPE, struct _tagSubscriptionInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180016f80`

## callees

- `0x180003950`
- `0x18000e110`
- `0x180016e18`
- `0x1800170c8`
- `0x18001be60`
- `0x18001cd88`
- `0x18002924e`
- `0x180029280`
- `0x180029310`

## import_xrefs

- `IEFRAME!__imp_SHRestricted2W` at `0x180016e8e`
- `IEFRAME!__imp_SHRestricted2W` at `0x180016e8e`

## pseudocode

```c
__int64 __fastcall CSubscriptionMgr::CreateDesktopSubscription(
        CSubscriptionMgr *this,
        HWND a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        enum SUBSCRIPTIONTYPE a6,
        struct _tagSubscriptionInfo *a7)
{
  struct _tagSubscriptionInfo *v11; // r15
  __int64 v12; // rcx
  __int64 v14; // rax
  _QWORD v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  enum SUBSCRIPTIONTYPE v16; // [rsp+60h] [rbp-A0h]
  unsigned int v17; // [rsp+64h] [rbp-9Ch]
  __int64 v18; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v19[104]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v20[2088]; // [rsp+E0h] [rbp-20h] BYREF

  v18 = 112;
  memset_0(v19, 0, sizeof(v19));
  v11 = (struct _tagSubscriptionInfo *)&v18;
  if ( a7 )
    v11 = a7;
  if ( (unsigned int)SHRestricted2W(1342177282, a3, 0) )
    return 2147500037LL;
  v16 = a6;
  v17 = a5;
  v15[0] = this;
  v15[1] = a4;
  v15[2] = a3;
  v15[3] = v11;
  StringCchCopyW(v20, 0x824u, a3);
  if ( !(unsigned int)IsHTTPPrefixed(v20) )
  {
    SGMessageBox(a2, 0x1F8Eu, 0x40u);
    return 2147942487LL;
  }
  v14 = DialogBoxParam(v12, 6002, a2, SummarizeDesktopSubscriptionDlgProc, v15);
  if ( v14 == -1 )
    return 2147500037LL;
  if ( v14 == 2 )
    return 1;
  return CSubscriptionMgr::CreateSubscriptionNoSummary(this, a2, a3, a4, a5 | 4, a6, v11);
}

```

## disassembly

```asm
0x180016e18  push    rbp
0x180016e1a  push    rbx
0x180016e1b  push    rsi
0x180016e1c  push    rdi
0x180016e1d  push    r12
0x180016e1f  push    r13
0x180016e21  push    r14
0x180016e23  push    r15
0x180016e25  lea     rbp, [rsp-1048h]
0x180016e2d  mov     eax, 1148h
0x180016e32  call    _alloca_probe
0x180016e37  sub     rsp, rax
0x180016e3a  mov     rax, cs:__security_cookie
0x180016e41  xor     rax, rsp
0x180016e44  mov     [rbp+1080h+var_50], rax
0x180016e4b  mov     rbx, [rbp+1080h+arg_30]
0x180016e52  mov     rdi, rdx
0x180016e55  xor     edx, edx; Val
0x180016e57  mov     [rsp+1180h+var_1110], 70h ; 'p'
0x180016e60  mov     rsi, r8
0x180016e63  mov     r12, rcx
0x180016e66  lea     rcx, [rsp+1180h+var_1108]; void *
0x180016e6b  mov     r13, r9
0x180016e6e  lea     r8d, [rdx+68h]; Size
0x180016e72  call    memset_0
0x180016e77  test    rbx, rbx
0x180016e7a  lea     r15, [rsp+1180h+var_1110]
0x180016e7f  mov     rdx, rsi
0x180016e82  mov     ecx, 50000002h
0x180016e87  cmovnz  r15, rbx
0x180016e8b  xor     r8d, r8d
0x180016e8e  call    cs:__imp_SHRestricted2W
0x180016e94  test    eax, eax
0x180016e96  jnz     loc_180016F51
0x180016e9c  mov     r14d, [rbp+1080h+arg_28]
0x180016ea3  lea     rcx, [rbp+1080h+var_10A0]; unsigned __int16 *
0x180016ea7  mov     ebx, [rbp+1080h+arg_20]
0x180016ead  mov     r8, rsi; unsigned __int16 *
0x180016eb0  mov     edx, 824h; unsigned __int64
0x180016eb5  mov     [rsp+1180h+var_1120], r14d
0x180016eba  mov     [rsp+1180h+var_111C], ebx
0x180016ebe  mov     [rsp+1180h+var_1140], r12
0x180016ec3  mov     [rsp+1180h+var_1138], r13
0x180016ec8  mov     [rsp+1180h+var_1130], rsi
0x180016ecd  mov     [rsp+1180h+var_1128], r15
0x180016ed2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016ed7  lea     rcx, [rbp+1080h+var_10A0]
0x180016edb  call    IsHTTPPrefixed
0x180016ee0  test    eax, eax
0x180016ee2  jnz     short loc_180016EFC
0x180016ee4  mov     edx, 1F8Eh; unsigned int
0x180016ee9  lea     r8d, [rax+40h]; unsigned int
0x180016eed  mov     rcx, rdi; hWnd
0x180016ef0  call    ?SGMessageBox@@YAHPEAUHWND__@@II@Z; SGMessageBox(HWND__ *,uint,uint)
0x180016ef5  mov     eax, 80070057h
0x180016efa  jmp     short loc_180016F56
0x180016efc  lea     rax, [rsp+1180h+var_1140]
0x180016f01  mov     r8, rdi
0x180016f04  lea     r9, ?SummarizeDesktopSubscriptionDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; SummarizeDesktopSubscriptionDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180016f0b  mov     qword ptr [rsp+1180h+var_1160], rax
0x180016f10  mov     edx, 1772h
0x180016f15  call    DialogBoxParam
0x180016f1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016f1e  jz      short loc_180016F51
0x180016f20  cmp     rax, 2
0x180016f24  jz      short loc_180016F4A
0x180016f26  or      ebx, 4
0x180016f29  mov     [rsp+1180h+var_1150], r15; struct _tagSubscriptionInfo *
0x180016f2e  mov     [rsp+1180h+var_1158], r14d; enum SUBSCRIPTIONTYPE
0x180016f33  mov     r9, r13; unsigned __int16 *
0x180016f36  mov     r8, rsi; unsigned __int16 *
0x180016f39  mov     dword ptr [rsp+1180h+var_1160], ebx; char
0x180016f3d  mov     rdx, rdi; HWND
0x180016f40  mov     rcx, r12; this
0x180016f43  call    ?CreateSubscriptionNoSummary@CSubscriptionMgr@@IEAAJPEAUHWND__@@PEBG1KW4SUBSCRIPTIONTYPE@@PEAU_tagSubscriptionInfo@@@Z; CSubscriptionMgr::CreateSubscriptionNoSummary(HWND__ *,ushort const *,ushort const *,ulong,SUBSCRIPTIONTYPE,_tagSubscriptionInfo *)
0x180016f48  jmp     short loc_180016F56
0x180016f4a  mov     eax, 1
0x180016f4f  jmp     short loc_180016F56
0x180016f51  mov     eax, 80004005h
0x180016f56  mov     rcx, [rbp+1080h+var_50]
0x180016f5d  xor     rcx, rsp; StackCookie
0x180016f60  call    __security_check_cookie
0x180016f65  add     rsp, 1148h
0x180016f6c  pop     r15
0x180016f6e  pop     r14
0x180016f70  pop     r13
0x180016f72  pop     r12
0x180016f74  pop     rdi
0x180016f75  pop     rsi
0x180016f76  pop     rbx
0x180016f77  pop     rbp
0x180016f78  retn
```
