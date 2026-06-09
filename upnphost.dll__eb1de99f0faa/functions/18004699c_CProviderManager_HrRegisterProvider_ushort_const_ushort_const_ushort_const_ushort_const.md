# CProviderManager::HrRegisterProvider(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18004699c`
- end: `0x180046b07`
- name: `?HrRegisterProvider@CProviderManager@@QEAAJPEBG000@Z`
- size: `363`
- prototype: `int(CProviderManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030160`
- `0x18004c6b0`

## callees

- `0x18001ab90`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x1800468cc`
- `0x18004699c`
- `0x180046c5c`
- `0x18004b270`
- `0x18004b2e0`
- `0x18004b608`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046aa8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046aa8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180046a2c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180046a2c`

## pseudocode

```c
__int64 __fastcall CProviderManager::HrRegisterProvider(
        CProviderManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int inserted; // ebx
  void *Block; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v12[24]; // [rsp+28h] [rbp-38h] BYREF
  GUID clsid; // [rsp+40h] [rbp-20h] BYREF

  if ( a2 && a3 && a4 && a5 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5686e3dd21e6358c4bb924a15afed3a0_Traceguids);
    clsid = 0;
    if ( CLSIDFromProgID(a3, &clsid) < 0 )
    {
      inserted = -2147024809;
    }
    else
    {
      Block = 0;
      inserted = CUString::HrAssign((CUString *)&Block, a2);
      if ( inserted >= 0 )
      {
        if ( CTable<CUString,CProvider>::Lookup(this, &Block) )
        {
          inserted = -2147180511;
        }
        else
        {
          CProvider::CProvider((CProvider *)v12);
          inserted = CProvider::HrInitialize((CProvider *)v12, a3, a4, a5);
          if ( inserted >= 0 )
            inserted = CTable<CUString,CProvider>::HrInsertTransfer(this, &Block, v12);
          CProvider::~CProvider((CProvider *)v12);
        }
      }
      free(Block);
      if ( !inserted )
        return (unsigned int)inserted;
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_5686e3dd21e6358c4bb924a15afed3a0_Traceguids,
        (unsigned int)inserted);
    return (unsigned int)inserted;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x18004699c  push    rbp
0x18004699e  push    rbx
0x18004699f  push    rsi
0x1800469a0  push    rdi
0x1800469a1  push    r12
0x1800469a3  push    r14
0x1800469a5  push    r15
0x1800469a7  mov     rbp, rsp
0x1800469aa  sub     rsp, 60h
0x1800469ae  mov     rax, cs:__security_cookie
0x1800469b5  xor     rax, rsp
0x1800469b8  mov     [rbp+var_10], rax
0x1800469bc  mov     r14, [rbp+arg_20]
0x1800469c0  mov     rsi, r9
0x1800469c3  mov     rdi, r8
0x1800469c6  mov     rbx, rdx
0x1800469c9  mov     r15, rcx
0x1800469cc  test    rdx, rdx
0x1800469cf  jz      loc_180046AE7
0x1800469d5  test    r8, r8
0x1800469d8  jz      loc_180046AE7
0x1800469de  test    r9, r9
0x1800469e1  jz      loc_180046AE7
0x1800469e7  test    r14, r14
0x1800469ea  jz      loc_180046AE7
0x1800469f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800469f7  lea     r12, WPP_GLOBAL_Control
0x1800469fe  cmp     rcx, r12
0x180046a01  jz      short loc_180046A1E
0x180046a03  test    byte ptr [rcx+1Ch], 40h
0x180046a07  jz      short loc_180046A1E
0x180046a09  mov     rcx, [rcx+10h]
0x180046a0d  lea     r8, WPP_5686e3dd21e6358c4bb924a15afed3a0_Traceguids
0x180046a14  mov     edx, 0Ch
0x180046a19  call    WPP_SF_
0x180046a1e  xorps   xmm0, xmm0
0x180046a21  lea     rdx, [rbp+clsid]; lpclsid
0x180046a25  mov     rcx, rdi; lpszProgID
0x180046a28  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180046a2c  call    cs:__imp_CLSIDFromProgID
0x180046a32  test    eax, eax
0x180046a34  js      short loc_180046AB4
0x180046a36  mov     rdx, rbx; unsigned __int16 *
0x180046a39  mov     [rbp+Block], 0
0x180046a41  lea     rcx, [rbp+Block]; this
0x180046a45  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180046a4a  mov     ebx, eax
0x180046a4c  test    eax, eax
0x180046a4e  js      short loc_180046AA4
0x180046a50  lea     rdx, [rbp+Block]
0x180046a54  mov     rcx, r15
0x180046a57  call    ?Lookup@?$CTable@VCUString@@VCProvider@@@@QEAAPEAVCProvider@@AEBVCUString@@@Z; CTable<CUString,CProvider>::Lookup(CUString const &)
0x180046a5c  test    rax, rax
0x180046a5f  jnz     short loc_180046A9F
0x180046a61  lea     rcx, [rbp+var_38]; this
0x180046a65  call    ??0CProvider@@QEAA@XZ; CProvider::CProvider(void)
0x180046a6a  mov     r9, r14; unsigned __int16 *
0x180046a6d  lea     rcx, [rbp+var_38]; this
0x180046a71  mov     r8, rsi; unsigned __int16 *
0x180046a74  mov     rdx, rdi; unsigned __int16 *
0x180046a77  call    ?HrInitialize@CProvider@@QEAAJPEBG00@Z; CProvider::HrInitialize(ushort const *,ushort const *,ushort const *)
0x180046a7c  mov     ebx, eax
0x180046a7e  test    eax, eax
0x180046a80  js      short loc_180046A94
0x180046a82  lea     r8, [rbp+var_38]
0x180046a86  mov     rcx, r15
0x180046a89  lea     rdx, [rbp+Block]
0x180046a8d  call    ?HrInsertTransfer@?$CTable@VCUString@@VCProvider@@@@QEAAJAEAVCUString@@AEAVCProvider@@@Z; CTable<CUString,CProvider>::HrInsertTransfer(CUString &,CProvider &)
0x180046a92  mov     ebx, eax
0x180046a94  lea     rcx, [rbp+var_38]; this
0x180046a98  call    ??1CProvider@@QEAA@XZ; CProvider::~CProvider(void)
0x180046a9d  jmp     short loc_180046AA4
0x180046a9f  mov     ebx, 8004A021h
0x180046aa4  mov     rcx, [rbp+Block]; Block
0x180046aa8  call    cs:__imp_free
0x180046aae  test    ebx, ebx
0x180046ab0  jz      short loc_180046AE3
0x180046ab2  jmp     short loc_180046AB9
0x180046ab4  mov     ebx, 80070057h
0x180046ab9  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ac0  cmp     rcx, r12
0x180046ac3  jz      short loc_180046AE3
0x180046ac5  test    byte ptr [rcx+1Ch], 1
0x180046ac9  jz      short loc_180046AE3
0x180046acb  mov     rcx, [rcx+10h]
0x180046acf  lea     r8, WPP_5686e3dd21e6358c4bb924a15afed3a0_Traceguids
0x180046ad6  mov     edx, 0Dh
0x180046adb  mov     r9d, ebx
0x180046ade  call    WPP_SF_d
0x180046ae3  mov     eax, ebx
0x180046ae5  jmp     short loc_180046AEC
0x180046ae7  mov     eax, 80004003h
0x180046aec  mov     rcx, [rbp+var_10]
0x180046af0  xor     rcx, rsp; StackCookie
0x180046af3  call    __security_check_cookie
0x180046af8  add     rsp, 60h
0x180046afc  pop     r15
0x180046afe  pop     r14
0x180046b00  pop     r12
0x180046b02  pop     rdi
0x180046b03  pop     rsi
0x180046b04  pop     rbx
0x180046b05  pop     rbp
0x180046b06  retn
```
