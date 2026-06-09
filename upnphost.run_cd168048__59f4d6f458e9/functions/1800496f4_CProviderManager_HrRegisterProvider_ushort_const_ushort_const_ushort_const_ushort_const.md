# CProviderManager::HrRegisterProvider(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800496f4`
- end: `0x180049870`
- name: `?HrRegisterProvider@CProviderManager@@QEAAJPEBG000@Z`
- size: `380`
- prototype: `__int64 __fastcall(CProviderManager *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031c70`
- `0x18004fa60`

## callees

- `0x18000f8a0`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180049618`
- `0x1800496f4`
- `0x1800499d0`
- `0x18004e520`
- `0x18004e590`
- `0x18004e8dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004980a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004980a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180049784`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180049784`

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
0x1800496f4  push    rbp
0x1800496f6  push    rbx
0x1800496f7  push    rsi
0x1800496f8  push    rdi
0x1800496f9  push    r12
0x1800496fb  push    r14
0x1800496fd  push    r15
0x1800496ff  mov     rbp, rsp
0x180049702  sub     rsp, 60h
0x180049706  mov     rax, cs:__security_cookie
0x18004970d  xor     rax, rsp
0x180049710  mov     [rbp+var_10], rax
0x180049714  mov     r14, [rbp+arg_20]
0x180049718  mov     rsi, r9
0x18004971b  mov     rdi, r8
0x18004971e  mov     rbx, rdx
0x180049721  mov     r15, rcx
0x180049724  test    rdx, rdx
0x180049727  jz      loc_18004984F
0x18004972d  test    r8, r8
0x180049730  jz      loc_18004984F
0x180049736  test    r9, r9
0x180049739  jz      loc_18004984F
0x18004973f  test    r14, r14
0x180049742  jz      loc_18004984F
0x180049748  mov     rcx, cs:WPP_GLOBAL_Control
0x18004974f  lea     r12, WPP_GLOBAL_Control
0x180049756  cmp     rcx, r12
0x180049759  jz      short loc_180049776
0x18004975b  test    byte ptr [rcx+1Ch], 40h
0x18004975f  jz      short loc_180049776
0x180049761  mov     rcx, [rcx+10h]
0x180049765  lea     r8, WPP_5686e3dd21e6358c4bb924a15afed3a0_Traceguids
0x18004976c  mov     edx, 0Ch
0x180049771  call    WPP_SF_
0x180049776  xorps   xmm0, xmm0
0x180049779  lea     rdx, [rbp+clsid]; lpclsid
0x18004977d  mov     rcx, rdi; lpszProgID
0x180049780  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180049784  call    cs:__imp_CLSIDFromProgID
0x18004978b  nop     dword ptr [rax+rax+00h]
0x180049790  test    eax, eax
0x180049792  js      loc_18004981C
0x180049798  mov     rdx, rbx; unsigned __int16 *
0x18004979b  mov     [rbp+Block], 0
0x1800497a3  lea     rcx, [rbp+Block]; this
0x1800497a7  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x1800497ac  mov     ebx, eax
0x1800497ae  test    eax, eax
0x1800497b0  js      short loc_180049806
0x1800497b2  lea     rdx, [rbp+Block]
0x1800497b6  mov     rcx, r15
0x1800497b9  call    ?Lookup@?$CTable@VCUString@@VCProvider@@@@QEAAPEAVCProvider@@AEBVCUString@@@Z; CTable<CUString,CProvider>::Lookup(CUString const &)
0x1800497be  test    rax, rax
0x1800497c1  jnz     short loc_180049801
0x1800497c3  lea     rcx, [rbp+var_38]; this
0x1800497c7  call    ??0CProvider@@QEAA@XZ; CProvider::CProvider(void)
0x1800497cc  mov     r9, r14; unsigned __int16 *
0x1800497cf  lea     rcx, [rbp+var_38]; this
0x1800497d3  mov     r8, rsi; unsigned __int16 *
0x1800497d6  mov     rdx, rdi; unsigned __int16 *
0x1800497d9  call    ?HrInitialize@CProvider@@QEAAJPEBG00@Z; CProvider::HrInitialize(ushort const *,ushort const *,ushort const *)
0x1800497de  mov     ebx, eax
0x1800497e0  test    eax, eax
0x1800497e2  js      short loc_1800497F6
0x1800497e4  lea     r8, [rbp+var_38]
0x1800497e8  mov     rcx, r15
0x1800497eb  lea     rdx, [rbp+Block]
0x1800497ef  call    ?HrInsertTransfer@?$CTable@VCUString@@VCProvider@@@@QEAAJAEAVCUString@@AEAVCProvider@@@Z; CTable<CUString,CProvider>::HrInsertTransfer(CUString &,CProvider &)
0x1800497f4  mov     ebx, eax
0x1800497f6  lea     rcx, [rbp+var_38]; this
0x1800497fa  call    ??1CProvider@@QEAA@XZ; CProvider::~CProvider(void)
0x1800497ff  jmp     short loc_180049806
0x180049801  mov     ebx, 8004A021h
0x180049806  mov     rcx, [rbp+Block]; Block
0x18004980a  call    cs:__imp_free
0x180049811  nop     dword ptr [rax+rax+00h]
0x180049816  test    ebx, ebx
0x180049818  jz      short loc_18004984B
0x18004981a  jmp     short loc_180049821
0x18004981c  mov     ebx, 80070057h
0x180049821  mov     rcx, cs:WPP_GLOBAL_Control
0x180049828  cmp     rcx, r12
0x18004982b  jz      short loc_18004984B
0x18004982d  test    byte ptr [rcx+1Ch], 1
0x180049831  jz      short loc_18004984B
0x180049833  mov     rcx, [rcx+10h]
0x180049837  lea     r8, WPP_5686e3dd21e6358c4bb924a15afed3a0_Traceguids
0x18004983e  mov     edx, 0Dh
0x180049843  mov     r9d, ebx
0x180049846  call    WPP_SF_d
0x18004984b  mov     eax, ebx
0x18004984d  jmp     short loc_180049854
0x18004984f  mov     eax, 80004003h
0x180049854  mov     rcx, [rbp+var_10]
0x180049858  xor     rcx, rsp; StackCookie
0x18004985b  call    __security_check_cookie
0x180049860  add     rsp, 60h
0x180049864  pop     r15
0x180049866  pop     r14
0x180049868  pop     r12
0x18004986a  pop     rdi
0x18004986b  pop     rsi
0x18004986c  pop     rbx
0x18004986d  pop     rbp
0x18004986e  retn
```
