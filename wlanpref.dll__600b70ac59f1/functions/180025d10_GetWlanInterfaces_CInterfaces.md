# GetWlanInterfaces(CInterfaces &)

- ea: `0x180025d10`
- end: `0x180025f74`
- name: `?GetWlanInterfaces@@YAJAEAVCInterfaces@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct CInterfaces *this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002447c`
- `0x180024d80`

## callees

- `0x1800036ac`
- `0x18000cf1c`
- `0x180020800`
- `0x180023054`
- `0x180025944`
- `0x180025c0c`
- `0x180025d10`

## import_xrefs

- `wlanapi!WlanCloseHandle` at `0x180025f18`
- `wlanapi!WlanCloseHandle` at `0x180025f18`
- `wlanapi!WlanFreeMemory` at `0x180025efd`
- `wlanapi!WlanFreeMemory` at `0x180025efd`
- `wlanapi!WlanEnumInterfaces` at `0x180025da1`
- `wlanapi!WlanEnumInterfaces` at `0x180025da1`
- `wlanapi!WlanOpenHandle` at `0x180025d87`
- `wlanapi!WlanOpenHandle` at `0x180025d87`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetWlanInterfaces(struct CInterfaces *this)
{
  DWORD v2; // eax
  int v3; // ebx
  WLAN_INTERFACE_INFO *InterfaceInfo; // rdi
  _QWORD *v5; // rcx
  DWORD v6; // esi
  __int64 v7; // rdx
  void *phClientHandle; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v10[8]; // [rsp+28h] [rbp-8h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+68h] [rbp+38h] BYREF
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+70h] [rbp+40h] BYREF
  char v13; // [rsp+78h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 17), 16, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  }
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  ppInterfaceList = 0;
  v2 = WlanOpenHandle(1u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v3 = v2;
  if ( v2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 145)
      || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
    {
      goto LABEL_24;
    }
    v7 = 19;
LABEL_22:
    WPP_SF_d(v5[17], v7, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids, v2);
LABEL_23:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_24;
  }
  v2 = WlanEnumInterfaces(phClientHandle, 0, &ppInterfaceList);
  v3 = v2;
  if ( v2 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !*((_BYTE *)WPP_GLOBAL_Control + 145)
      || (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) == 0 )
    {
      goto LABEL_24;
    }
    v7 = 18;
    goto LABEL_22;
  }
  InterfaceInfo = ppInterfaceList->InterfaceInfo;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 145) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      17,
      WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids,
      ppInterfaceList->dwNumberOfItems);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = 0;
  if ( ppInterfaceList->dwNumberOfItems )
  {
    do
    {
      WTL::CString::CString((WTL::CString *)&v13, InterfaceInfo->strInterfaceDescription);
      GetAdapterFriendlyName(v10, InterfaceInfo, &v13);
      CInterfaces::Add(this, &InterfaceInfo->InterfaceGuid, (struct WTL::CString *)&v13, (struct WTL::CString *)v10);
      WTL::CString::~CString((WTL::CString *)v10);
      WTL::CString::~CString((WTL::CString *)&v13);
      ++v6;
      ++InterfaceInfo;
    }
    while ( v6 < ppInterfaceList->dwNumberOfItems );
    goto LABEL_23;
  }
LABEL_24:
  if ( ppInterfaceList )
  {
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 145) >= 3u && (*((_BYTE *)v5 + 148) & 1) != 0 )
      WPP_SF_(v5[17], 20, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
    WlanFreeMemory(ppInterfaceList);
    v5 = WPP_GLOBAL_Control;
  }
  if ( phClientHandle )
  {
    WlanCloseHandle(phClientHandle, 0);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 145) >= 4u && (*((_BYTE *)v5 + 148) & 1) != 0 )
    WPP_SF_(v5[17], 21, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids);
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180025d10  mov     [rsp-28h+arg_0], rbx
0x180025d15  push    rbp
0x180025d16  push    rsi
0x180025d17  push    rdi
0x180025d18  push    r13
0x180025d1a  push    r14
0x180025d1c  mov     rbp, rsp
0x180025d1f  sub     rsp, 30h
0x180025d23  mov     r14, rcx
0x180025d26  lea     r13, WPP_GLOBAL_Control
0x180025d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d34  cmp     rcx, r13
0x180025d37  jz      short loc_180025D63
0x180025d39  cmp     byte ptr [rcx+91h], 4
0x180025d40  jb      short loc_180025D63
0x180025d42  test    byte ptr [rcx+94h], 1
0x180025d49  jz      short loc_180025D63
0x180025d4b  mov     edx, 10h
0x180025d50  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025d57  mov     rcx, [rcx+88h]
0x180025d5e  call    WPP_SF_
0x180025d63  mov     [rbp+phClientHandle], 0
0x180025d6b  mov     [rbp+pdwNegotiatedVersion], 0
0x180025d72  mov     [rbp+ppInterfaceList], 0
0x180025d7a  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180025d7e  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180025d82  xor     edx, edx; pReserved
0x180025d84  lea     ecx, [rdx+1]; dwClientVersion
0x180025d87  call    cs:__imp_WlanOpenHandle
0x180025d8d  mov     ebx, eax
0x180025d8f  test    eax, eax
0x180025d91  jnz     loc_180025E83
0x180025d97  lea     r8, [rbp+ppInterfaceList]; ppInterfaceList
0x180025d9b  xor     edx, edx; pReserved
0x180025d9d  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180025da1  call    cs:__imp_WlanEnumInterfaces
0x180025da7  mov     ebx, eax
0x180025da9  test    eax, eax
0x180025dab  jnz     loc_180025E5E
0x180025db1  mov     r9, [rbp+ppInterfaceList]
0x180025db5  lea     rdi, [r9+8]
0x180025db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025dc0  cmp     rcx, r13
0x180025dc3  jz      short loc_180025DF7
0x180025dc5  cmp     byte ptr [rcx+91h], 3
0x180025dcc  jb      short loc_180025DF7
0x180025dce  test    byte ptr [rcx+94h], 1
0x180025dd5  jz      short loc_180025DF7
0x180025dd7  lea     edx, [rax+11h]
0x180025dda  mov     r9d, [r9]
0x180025ddd  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025de4  mov     rcx, [rcx+88h]
0x180025deb  call    WPP_SF_d
0x180025df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025df7  xor     esi, esi
0x180025df9  mov     rax, [rbp+ppInterfaceList]
0x180025dfd  cmp     [rax], esi
0x180025dff  jbe     loc_180025EC3
0x180025e05  lea     rdx, [rdi+10h]; Source
0x180025e09  lea     rcx, [rbp+arg_18]; this
0x180025e0d  call    ??0CString@WTL@@QEAA@PEBG@Z; WTL::CString::CString(ushort const *)
0x180025e12  nop
0x180025e13  lea     r8, [rbp+arg_18]
0x180025e17  mov     rdx, rdi
0x180025e1a  lea     rcx, [rbp+var_8]
0x180025e1e  call    ?GetAdapterFriendlyName@@YA?AVCString@WTL@@AEAU_GUID@@AEAV12@@Z; GetAdapterFriendlyName(_GUID &,WTL::CString &)
0x180025e23  nop
0x180025e24  lea     r9, [rbp+var_8]; struct WTL::CString *
0x180025e28  lea     r8, [rbp+arg_18]; struct WTL::CString *
0x180025e2c  mov     rdx, rdi; struct _GUID *
0x180025e2f  mov     rcx, r14; this
0x180025e32  call    ?Add@CInterfaces@@QEAA_NAEAU_GUID@@AEAVCString@WTL@@1@Z; CInterfaces::Add(_GUID &,WTL::CString &,WTL::CString &)
0x180025e37  nop
0x180025e38  lea     rcx, [rbp+var_8]; this
0x180025e3c  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180025e41  nop
0x180025e42  lea     rcx, [rbp+arg_18]; this
0x180025e46  call    ??1CString@WTL@@QEAA@XZ; WTL::CString::~CString(void)
0x180025e4b  inc     esi
0x180025e4d  add     rdi, 214h
0x180025e54  mov     rax, [rbp+ppInterfaceList]
0x180025e58  cmp     esi, [rax]
0x180025e5a  jb      short loc_180025E05
0x180025e5c  jmp     short loc_180025EBC
0x180025e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e65  cmp     rcx, r13
0x180025e68  jz      short loc_180025EC3
0x180025e6a  cmp     byte ptr [rcx+91h], 1
0x180025e71  jb      short loc_180025EC3
0x180025e73  test    byte ptr [rcx+94h], 1
0x180025e7a  jz      short loc_180025EC3
0x180025e7c  mov     edx, 12h
0x180025e81  jmp     short loc_180025EA6
0x180025e83  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e8a  cmp     rcx, r13
0x180025e8d  jz      short loc_180025EC3
0x180025e8f  cmp     byte ptr [rcx+91h], 1
0x180025e96  jb      short loc_180025EC3
0x180025e98  test    byte ptr [rcx+94h], 1
0x180025e9f  jz      short loc_180025EC3
0x180025ea1  mov     edx, 13h
0x180025ea6  mov     r9d, eax
0x180025ea9  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025eb0  mov     rcx, [rcx+88h]
0x180025eb7  call    WPP_SF_d
0x180025ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ec3  cmp     [rbp+ppInterfaceList], 0
0x180025ec8  jz      short loc_180025F0A
0x180025eca  cmp     rcx, r13
0x180025ecd  jz      short loc_180025EF9
0x180025ecf  cmp     byte ptr [rcx+91h], 3
0x180025ed6  jb      short loc_180025EF9
0x180025ed8  test    byte ptr [rcx+94h], 1
0x180025edf  jz      short loc_180025EF9
0x180025ee1  mov     edx, 14h
0x180025ee6  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025eed  mov     rcx, [rcx+88h]
0x180025ef4  call    WPP_SF_
0x180025ef9  mov     rcx, [rbp+ppInterfaceList]; pMemory
0x180025efd  call    cs:__imp_WlanFreeMemory
0x180025f03  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f0a  mov     rax, [rbp+phClientHandle]
0x180025f0e  test    rax, rax
0x180025f11  jz      short loc_180025F25
0x180025f13  xor     edx, edx; pReserved
0x180025f15  mov     rcx, rax; hClientHandle
0x180025f18  call    cs:__imp_WlanCloseHandle
0x180025f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f25  cmp     rcx, r13
0x180025f28  jz      short loc_180025F54
0x180025f2a  cmp     byte ptr [rcx+91h], 4
0x180025f31  jb      short loc_180025F54
0x180025f33  test    byte ptr [rcx+94h], 1
0x180025f3a  jz      short loc_180025F54
0x180025f3c  mov     edx, 15h
0x180025f41  lea     r8, WPP_f20f06ec2a2b3843231d270c9803a965_Traceguids
0x180025f48  mov     rcx, [rcx+88h]
0x180025f4f  call    WPP_SF_
0x180025f54  test    ebx, ebx
0x180025f56  jle     short loc_180025F61
0x180025f58  movzx   ebx, bx
0x180025f5b  or      ebx, 80070000h
0x180025f61  mov     eax, ebx
0x180025f63  mov     rbx, [rsp+30h+arg_0]
0x180025f68  add     rsp, 30h
0x180025f6c  pop     r14
0x180025f6e  pop     r13
0x180025f70  pop     rdi
0x180025f71  pop     rsi
0x180025f72  pop     rbp
0x180025f73  retn
```
