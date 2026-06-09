# CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)

- ea: `0x180046de8`
- end: `0x180046fd7`
- name: `?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z`
- size: `495`
- prototype: `int(CDeviceManager *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030160`
- `0x18004c230`
- `0x18004cb90`

## callees

- `0x18001ab90`
- `0x18002c080`
- `0x18002c1ac`
- `0x1800384c4`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x180046540`
- `0x180046de8`
- `0x180047150`
- `0x18004b7bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046f66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180046f66`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180046e89`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180046e89`

## pseudocode

```c
__int64 __fastcall CDeviceManager::HrAddDevice(
        CDeviceManager *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        int a6,
        unsigned __int16 **a7)
{
  HRESULT v11; // eax
  STRSAFE_PCNZWCH v12; // rcx
  int inserted; // ebx
  __int64 i; // rdi
  const unsigned __int16 *v15; // rdx
  _BYTE v17[80]; // [rsp+30h] [rbp-B8h] BYREF
  GUID clsid; // [rsp+80h] [rbp-68h] BYREF

  if ( a3 && a4 && a5 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids);
    clsid = 0;
    v11 = CLSIDFromProgID(a3, &clsid);
    if ( v11 >= 0 )
    {
      CPhysicalDeviceInfo::CPhysicalDeviceInfo((CPhysicalDeviceInfo *)v17);
      inserted = CPhysicalDeviceInfo::HrInitialize((CPhysicalDeviceInfo *)v17, a3, a4, a5, a6, a7);
      if ( inserted >= 0 )
      {
        inserted = CTable<_GUID,CPhysicalDeviceInfo>::HrInsertTransfer(this, a2, v17);
        if ( inserted >= 0 )
        {
          for ( i = 0; (int)i < a6; i = (unsigned int)(i + 1) )
          {
            if ( inserted < 0 )
              break;
            v15 = a7[i];
            *(_QWORD *)&clsid.Data1 = 0;
            inserted = CUString::HrAssign((CUString *)&clsid, v15);
            if ( inserted >= 0 )
              inserted = CTable<CUString,_GUID>::HrInsertTransfer((char *)this + 32, &clsid, a2);
            free(*(void **)&clsid.Data1);
          }
        }
      }
      CPhysicalDeviceInfo::~CPhysicalDeviceInfo((CPhysicalDeviceInfo *)v17);
      if ( !inserted )
        return (unsigned int)inserted;
      v12 = WPP_GLOBAL_Control;
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 0x40) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          (unsigned int)WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids,
          (_DWORD)a3,
          v11);
        v12 = WPP_GLOBAL_Control;
      }
      inserted = -2147024809;
    }
    if ( v12 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v12[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 14, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids, (unsigned int)inserted);
    return (unsigned int)inserted;
  }
  return 2147500035LL;
}

```

## disassembly

```asm
0x180046de8  push    rbx
0x180046dea  push    rbp
0x180046deb  push    rsi
0x180046dec  push    rdi
0x180046ded  push    r12
0x180046def  push    r13
0x180046df1  push    r14
0x180046df3  push    r15
0x180046df5  sub     rsp, 0A8h
0x180046dfc  mov     rax, cs:__security_cookie
0x180046e03  xor     rax, rsp
0x180046e06  mov     [rsp+0E8h+var_58], rax
0x180046e0e  mov     rbp, [rsp+0E8h+arg_20]
0x180046e16  mov     rdi, r9
0x180046e19  mov     r12, [rsp+0E8h+arg_30]
0x180046e21  mov     rbx, r8
0x180046e24  mov     r15, rdx
0x180046e27  mov     r14, rcx
0x180046e2a  test    r8, r8
0x180046e2d  jz      loc_180046FAE
0x180046e33  test    r9, r9
0x180046e36  jz      loc_180046FAE
0x180046e3c  test    rbp, rbp
0x180046e3f  jz      loc_180046FAE
0x180046e45  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e4c  lea     r13, WPP_GLOBAL_Control
0x180046e53  cmp     rcx, r13
0x180046e56  jz      short loc_180046E73
0x180046e58  test    byte ptr [rcx+1Ch], 40h
0x180046e5c  jz      short loc_180046E73
0x180046e5e  mov     rcx, [rcx+10h]
0x180046e62  lea     r8, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids
0x180046e69  mov     edx, 0Ch
0x180046e6e  call    WPP_SF_
0x180046e73  xorps   xmm0, xmm0
0x180046e76  lea     rdx, [rsp+0E8h+clsid]; lpclsid
0x180046e7e  mov     rcx, rbx; lpszProgID
0x180046e81  movups  xmmword ptr [rsp+0E8h+clsid.Data1], xmm0
0x180046e89  call    cs:__imp_CLSIDFromProgID
0x180046e8f  test    eax, eax
0x180046e91  jns     short loc_180046ED2
0x180046e93  mov     rcx, cs:WPP_GLOBAL_Control
0x180046e9a  cmp     rcx, r13
0x180046e9d  jz      short loc_180046EC8
0x180046e9f  test    byte ptr [rcx+1Ch], 40h
0x180046ea3  jz      short loc_180046EC8
0x180046ea5  mov     rcx, [rcx+10h]
0x180046ea9  lea     r8, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids
0x180046eb0  mov     edx, 0Dh
0x180046eb5  mov     [rsp+0E8h+var_C8], eax
0x180046eb9  mov     r9, rbx
0x180046ebc  call    WPP_SF_Sd
0x180046ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ec8  mov     ebx, 80070057h
0x180046ecd  jmp     loc_180046F87
0x180046ed2  lea     rcx, [rsp+0E8h+var_B8]; this
0x180046ed7  call    ??0CPhysicalDeviceInfo@@QEAA@XZ; CPhysicalDeviceInfo::CPhysicalDeviceInfo(void)
0x180046edc  mov     esi, [rsp+0E8h+arg_28]
0x180046ee3  lea     rcx, [rsp+0E8h+var_B8]; this
0x180046ee8  mov     r9, rbp; unsigned __int16 *
0x180046eeb  mov     [rsp+0E8h+var_C0], r12; unsigned __int16 **
0x180046ef0  mov     r8, rdi; unsigned __int16 *
0x180046ef3  mov     [rsp+0E8h+var_C8], esi; int
0x180046ef7  mov     rdx, rbx; unsigned __int16 *
0x180046efa  call    ?HrInitialize@CPhysicalDeviceInfo@@QEAAJPEBG00JQEAPEAG@Z; CPhysicalDeviceInfo::HrInitialize(ushort const *,ushort const *,ushort const *,long,ushort * * const)
0x180046eff  mov     ebx, eax
0x180046f01  test    eax, eax
0x180046f03  js      short loc_180046F72
0x180046f05  lea     r8, [rsp+0E8h+var_B8]
0x180046f0a  mov     rdx, r15
0x180046f0d  mov     rcx, r14
0x180046f10  call    ?HrInsertTransfer@?$CTable@U_GUID@@VCPhysicalDeviceInfo@@@@QEAAJAEAU_GUID@@AEAVCPhysicalDeviceInfo@@@Z; CTable<_GUID,CPhysicalDeviceInfo>::HrInsertTransfer(_GUID &,CPhysicalDeviceInfo &)
0x180046f15  mov     ebx, eax
0x180046f17  test    eax, eax
0x180046f19  js      short loc_180046F72
0x180046f1b  xor     edi, edi
0x180046f1d  test    esi, esi
0x180046f1f  jle     short loc_180046F72
0x180046f21  test    ebx, ebx
0x180046f23  js      short loc_180046F72
0x180046f25  mov     rdx, [r12+rdi*8]; unsigned __int16 *
0x180046f29  lea     rcx, [rsp+0E8h+clsid]; this
0x180046f31  mov     qword ptr [rsp+0E8h+clsid.Data1], 0
0x180046f3d  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180046f42  mov     ebx, eax
0x180046f44  test    eax, eax
0x180046f46  js      short loc_180046F5E
0x180046f48  lea     rcx, [r14+20h]
0x180046f4c  mov     r8, r15
0x180046f4f  lea     rdx, [rsp+0E8h+clsid]
0x180046f57  call    ?HrInsertTransfer@?$CTable@VCUString@@U_GUID@@@@QEAAJAEAVCUString@@AEAU_GUID@@@Z; CTable<CUString,_GUID>::HrInsertTransfer(CUString &,_GUID &)
0x180046f5c  mov     ebx, eax
0x180046f5e  mov     rcx, qword ptr [rsp+0E8h+clsid.Data1]; Block
0x180046f66  call    cs:__imp_free
0x180046f6c  inc     edi
0x180046f6e  cmp     edi, esi
0x180046f70  jl      short loc_180046F21
0x180046f72  lea     rcx, [rsp+0E8h+var_B8]; this
0x180046f77  call    ??1CPhysicalDeviceInfo@@QEAA@XZ; CPhysicalDeviceInfo::~CPhysicalDeviceInfo(void)
0x180046f7c  test    ebx, ebx
0x180046f7e  jz      short loc_180046FAA
0x180046f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180046f87  cmp     rcx, r13
0x180046f8a  jz      short loc_180046FAA
0x180046f8c  test    byte ptr [rcx+1Ch], 1
0x180046f90  jz      short loc_180046FAA
0x180046f92  mov     rcx, [rcx+10h]
0x180046f96  lea     r8, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids
0x180046f9d  mov     edx, 0Eh
0x180046fa2  mov     r9d, ebx
0x180046fa5  call    WPP_SF_d
0x180046faa  mov     eax, ebx
0x180046fac  jmp     short loc_180046FB3
0x180046fae  mov     eax, 80004003h
0x180046fb3  mov     rcx, [rsp+0E8h+var_58]
0x180046fbb  xor     rcx, rsp; StackCookie
0x180046fbe  call    __security_check_cookie
0x180046fc3  add     rsp, 0A8h
0x180046fca  pop     r15
0x180046fcc  pop     r14
0x180046fce  pop     r13
0x180046fd0  pop     r12
0x180046fd2  pop     rdi
0x180046fd3  pop     rsi
0x180046fd4  pop     rbp
0x180046fd5  pop     rbx
0x180046fd6  retn
```
