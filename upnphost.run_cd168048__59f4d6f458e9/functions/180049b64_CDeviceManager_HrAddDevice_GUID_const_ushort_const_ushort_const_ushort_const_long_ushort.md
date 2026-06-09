# CDeviceManager::HrAddDevice(_GUID const &,ushort const *,ushort const *,ushort const *,long,ushort * *)

- ea: `0x180049b64`
- end: `0x180049d60`
- name: `?HrAddDevice@CDeviceManager@@QEAAJAEBU_GUID@@PEBG11JPEAPEAG@Z`
- size: `508`
- prototype: `int(CDeviceManager *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031c70`
- `0x18004f5b0`
- `0x18004ff50`

## callees

- `0x18000f8a0`
- `0x18002d870`
- `0x18002d9cc`
- `0x18003a8b4`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x180049258`
- `0x180049b64`
- `0x180049ee8`
- `0x18004eaa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049ce8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180049ce8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180049c05`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x180049c05`

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
0x180049b64  push    rbx
0x180049b66  push    rbp
0x180049b67  push    rsi
0x180049b68  push    rdi
0x180049b69  push    r12
0x180049b6b  push    r13
0x180049b6d  push    r14
0x180049b6f  push    r15
0x180049b71  sub     rsp, 0A8h
0x180049b78  mov     rax, cs:__security_cookie
0x180049b7f  xor     rax, rsp
0x180049b82  mov     [rsp+0E8h+var_58], rax
0x180049b8a  mov     rbp, [rsp+0E8h+arg_20]
0x180049b92  mov     rdi, r9
0x180049b95  mov     r12, [rsp+0E8h+arg_30]
0x180049b9d  mov     rbx, r8
0x180049ba0  mov     r15, rdx
0x180049ba3  mov     r14, rcx
0x180049ba6  test    r8, r8
0x180049ba9  jz      loc_180049D36
0x180049baf  test    r9, r9
0x180049bb2  jz      loc_180049D36
0x180049bb8  test    rbp, rbp
0x180049bbb  jz      loc_180049D36
0x180049bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180049bc8  lea     r13, WPP_GLOBAL_Control
0x180049bcf  cmp     rcx, r13
0x180049bd2  jz      short loc_180049BEF
0x180049bd4  test    byte ptr [rcx+1Ch], 40h
0x180049bd8  jz      short loc_180049BEF
0x180049bda  mov     rcx, [rcx+10h]
0x180049bde  lea     r8, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids
0x180049be5  mov     edx, 0Ch
0x180049bea  call    WPP_SF_
0x180049bef  xorps   xmm0, xmm0
0x180049bf2  lea     rdx, [rsp+0E8h+clsid]; lpclsid
0x180049bfa  mov     rcx, rbx; lpszProgID
0x180049bfd  movups  xmmword ptr [rsp+0E8h+clsid.Data1], xmm0
0x180049c05  call    cs:__imp_CLSIDFromProgID
0x180049c0c  nop     dword ptr [rax+rax+00h]
0x180049c11  test    eax, eax
0x180049c13  jns     short loc_180049C54
0x180049c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c1c  cmp     rcx, r13
0x180049c1f  jz      short loc_180049C4A
0x180049c21  test    byte ptr [rcx+1Ch], 40h
0x180049c25  jz      short loc_180049C4A
0x180049c27  mov     rcx, [rcx+10h]
0x180049c2b  lea     r8, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids
0x180049c32  mov     edx, 0Dh
0x180049c37  mov     [rsp+0E8h+var_C8], eax
0x180049c3b  mov     r9, rbx
0x180049c3e  call    WPP_SF_Sd
0x180049c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180049c4a  mov     ebx, 80070057h
0x180049c4f  jmp     loc_180049D0F
0x180049c54  lea     rcx, [rsp+0E8h+var_B8]; this
0x180049c59  call    ??0CPhysicalDeviceInfo@@QEAA@XZ; CPhysicalDeviceInfo::CPhysicalDeviceInfo(void)
0x180049c5e  mov     esi, [rsp+0E8h+arg_28]
0x180049c65  lea     rcx, [rsp+0E8h+var_B8]; this
0x180049c6a  mov     r9, rbp; unsigned __int16 *
0x180049c6d  mov     [rsp+0E8h+var_C0], r12; unsigned __int16 **
0x180049c72  mov     r8, rdi; unsigned __int16 *
0x180049c75  mov     [rsp+0E8h+var_C8], esi; int
0x180049c79  mov     rdx, rbx; unsigned __int16 *
0x180049c7c  call    ?HrInitialize@CPhysicalDeviceInfo@@QEAAJPEBG00JQEAPEAG@Z; CPhysicalDeviceInfo::HrInitialize(ushort const *,ushort const *,ushort const *,long,ushort * * const)
0x180049c81  mov     ebx, eax
0x180049c83  test    eax, eax
0x180049c85  js      short loc_180049CFA
0x180049c87  lea     r8, [rsp+0E8h+var_B8]
0x180049c8c  mov     rdx, r15
0x180049c8f  mov     rcx, r14
0x180049c92  call    ?HrInsertTransfer@?$CTable@U_GUID@@VCPhysicalDeviceInfo@@@@QEAAJAEAU_GUID@@AEAVCPhysicalDeviceInfo@@@Z; CTable<_GUID,CPhysicalDeviceInfo>::HrInsertTransfer(_GUID &,CPhysicalDeviceInfo &)
0x180049c97  mov     ebx, eax
0x180049c99  test    eax, eax
0x180049c9b  js      short loc_180049CFA
0x180049c9d  xor     edi, edi
0x180049c9f  test    esi, esi
0x180049ca1  jle     short loc_180049CFA
0x180049ca3  test    ebx, ebx
0x180049ca5  js      short loc_180049CFA
0x180049ca7  mov     rdx, [r12+rdi*8]; unsigned __int16 *
0x180049cab  lea     rcx, [rsp+0E8h+clsid]; this
0x180049cb3  mov     qword ptr [rsp+0E8h+clsid.Data1], 0
0x180049cbf  call    ?HrAssign@CUString@@QEAAJPEBG@Z; CUString::HrAssign(ushort const *)
0x180049cc4  mov     ebx, eax
0x180049cc6  test    eax, eax
0x180049cc8  js      short loc_180049CE0
0x180049cca  lea     rcx, [r14+20h]
0x180049cce  mov     r8, r15
0x180049cd1  lea     rdx, [rsp+0E8h+clsid]
0x180049cd9  call    ?HrInsertTransfer@?$CTable@VCUString@@U_GUID@@@@QEAAJAEAVCUString@@AEAU_GUID@@@Z; CTable<CUString,_GUID>::HrInsertTransfer(CUString &,_GUID &)
0x180049cde  mov     ebx, eax
0x180049ce0  mov     rcx, qword ptr [rsp+0E8h+clsid.Data1]; Block
0x180049ce8  call    cs:__imp_free
0x180049cef  nop     dword ptr [rax+rax+00h]
0x180049cf4  inc     edi
0x180049cf6  cmp     edi, esi
0x180049cf8  jl      short loc_180049CA3
0x180049cfa  lea     rcx, [rsp+0E8h+var_B8]; this
0x180049cff  call    ??1CPhysicalDeviceInfo@@QEAA@XZ; CPhysicalDeviceInfo::~CPhysicalDeviceInfo(void)
0x180049d04  test    ebx, ebx
0x180049d06  jz      short loc_180049D32
0x180049d08  mov     rcx, cs:WPP_GLOBAL_Control
0x180049d0f  cmp     rcx, r13
0x180049d12  jz      short loc_180049D32
0x180049d14  test    byte ptr [rcx+1Ch], 1
0x180049d18  jz      short loc_180049D32
0x180049d1a  mov     rcx, [rcx+10h]
0x180049d1e  lea     r8, WPP_45a1a04ba27e3c772afd4a47c42f6220_Traceguids
0x180049d25  mov     edx, 0Eh
0x180049d2a  mov     r9d, ebx
0x180049d2d  call    WPP_SF_d
0x180049d32  mov     eax, ebx
0x180049d34  jmp     short loc_180049D3B
0x180049d36  mov     eax, 80004003h
0x180049d3b  mov     rcx, [rsp+0E8h+var_58]
0x180049d43  xor     rcx, rsp; StackCookie
0x180049d46  call    __security_check_cookie
0x180049d4b  add     rsp, 0A8h
0x180049d52  pop     r15
0x180049d54  pop     r14
0x180049d56  pop     r13
0x180049d58  pop     r12
0x180049d5a  pop     rdi
0x180049d5b  pop     rsi
0x180049d5c  pop     rbp
0x180049d5d  pop     rbx
0x180049d5e  retn
```
