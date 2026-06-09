# CDevicesDB::DeleteAllNewDevices(ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,int,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)

- ea: `0x14000faac`
- end: `0x140010231`
- name: `?DeleteAllNewDevices@CDevicesDB@@QEAAJAEBV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@3@HAEAV23@@Z`
- size: `1925`
- prototype: `__int64 __usercall@<rax>(CDevicesDB *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x140052250`

## callees

- `0x1400065e0`
- `0x140006d70`
- `0x140008eac`
- `0x14000c920`
- `0x14000cb08`
- `0x14000e20c`
- `0x14000e3c8`
- `0x14000efe4`
- `0x14000faac`
- `0x1400105a0`
- `0x140010664`
- `0x140011594`
- `0x140015100`
- `0x140020e54`
- `0x14002f644`
- `0x14002f6dc`
- `0x140032eec`
- `0x14003e5f4`
- `0x14003f17c`
- `0x14004a834`
- `0x140054534`
- `0x140095fe8`
- `0x140097154`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400100a0`
- `ADVAPI32!RegCloseKey` at `0x14001010e`
- `ADVAPI32!RegCloseKey` at `0x1400100a0`
- `ADVAPI32!RegCloseKey` at `0x14001010e`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ffa1`
- `ADVAPI32!RegOpenKeyExW` at `0x14000ffa1`
- `ADVAPI32!RegQueryValueExW` at `0x14001002a`
- `ADVAPI32!RegQueryValueExW` at `0x14001002a`
- `KERNEL32!RaiseException` at `0x1400101e8`
- `KERNEL32!RaiseException` at `0x1400101fe`
- `KERNEL32!RaiseException` at `0x140010214`
- `KERNEL32!RaiseException` at `0x14001022a`
- `KERNEL32!RaiseException` at `0x1400101e8`
- `KERNEL32!RaiseException` at `0x1400101fe`
- `KERNEL32!RaiseException` at `0x140010214`
- `KERNEL32!RaiseException` at `0x14001022a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDevicesDB::DeleteAllNewDevices(CDevicesDB *this, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned int AllIDs; // eax
  unsigned int v6; // esi
  PVOID *v7; // r10
  const WCHAR *v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // eax
  _QWORD v12[2]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v13[2]; // [rsp+70h] [rbp-9h] BYREF
  _QWORD v14[9]; // [rsp+80h] [rbp+7h] BYREF
  unsigned int v15; // [rsp+F0h] [rbp+77h]

  v15 = a4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ddl(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *(unsigned int *)(a2 + 8), *(_DWORD *)(a3 + 16));
  }
  v15 = 0;
  v12[0] = 0;
  v12[1] = 0;
  AllIDs = CDevicesDB::GetAllIDs(this);
  v6 = AllIDs;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, AllIDs);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13[0] = 0;
  v13[1] = 0;
  if ( !v6 )
  {
    if ( (*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)this + 88LL))(this) )
    {
      memset(v14, 0, 24);
      v8 = (const WCHAR *)(*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)this + 88LL))(this);
      v9 = ATL::CRegKey::Open((ATL::CRegKey *)v14, HKEY_LOCAL_MACHINE, v8, 0x20119u);
      v6 = v9;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, v9);
      }
      if ( !v6 )
      {
        v10 = EnumSubKeys(v14, v13);
        v6 = v10;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, v10);
        }
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v14);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v7 + 28) & 1) != 0
    && *((unsigned __int8 *)v7 + 25) >= (unsigned int)(v6 != 0 ? 2 : 5) )
  {
    WPP_SF_Dd(v7[2], 155, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, v6);
  }
  ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(v13);
  ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(v12);
  return v6;
}

```

## disassembly

```asm
0x14000faac  mov     rax, rsp
0x14000faaf  mov     [rax+8], rbx
0x14000fab3  mov     [rax+20h], r9d
0x14000fab7  mov     [rax+18h], r8
0x14000fabb  mov     [rax+10h], rdx
0x14000fabf  push    rbp
0x14000fac0  push    rsi
0x14000fac1  push    rdi
0x14000fac2  push    r12
0x14000fac4  push    r13
0x14000fac6  push    r14
0x14000fac8  push    r15
0x14000faca  lea     rbp, [rax-57h]
0x14000face  sub     rsp, 90h
0x14000fad5  mov     r15, r8
0x14000fad8  mov     r12, rcx
0x14000fadb  lea     rbx, WPP_GLOBAL_Control
0x14000fae2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fae9  cmp     rcx, rbx
0x14000faec  jz      short loc_14000FB0F
0x14000faee  test    byte ptr [rcx+1Ch], 1
0x14000faf2  jz      short loc_14000FB0F
0x14000faf4  cmp     byte ptr [rcx+19h], 5
0x14000faf8  jb      short loc_14000FB0F
0x14000fafa  mov     eax, [r8+10h]
0x14000fafe  mov     dword ptr [rsp+0C0h+phkResult], eax
0x14000fb02  mov     r9d, [rdx+8]
0x14000fb06  mov     rcx, [rcx+10h]
0x14000fb0a  call    WPP_SF_ddl
0x14000fb0f  mov     [rbp+4Fh+arg_18], 0
0x14000fb16  mov     [rbp+4Fh+var_88], 0
0x14000fb1e  mov     [rbp+4Fh+var_80], 0
0x14000fb26  lea     rdx, [rbp+4Fh+var_88]
0x14000fb2a  mov     rcx, r12; this
0x14000fb2d  call    ?GetAllIDs@CDevicesDB@@QEAAJAEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CDevicesDB::GetAllIDs(ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)
0x14000fb32  mov     esi, eax
0x14000fb34  mov     r10, cs:WPP_GLOBAL_Control
0x14000fb3b  cmp     r10, rbx
0x14000fb3e  jz      short loc_14000FB6D
0x14000fb40  test    byte ptr [r10+1Ch], 2
0x14000fb45  jz      short loc_14000FB6D
0x14000fb47  cmp     byte ptr [r10+19h], 4
0x14000fb4c  jb      short loc_14000FB6D
0x14000fb4e  mov     edx, 90h
0x14000fb53  mov     r9d, eax
0x14000fb56  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000fb5d  mov     rcx, [r10+10h]
0x14000fb61  call    WPP_SF_d
0x14000fb66  mov     r10, cs:WPP_GLOBAL_Control
0x14000fb6d  mov     [rbp+4Fh+var_58], 0
0x14000fb75  mov     [rbp+4Fh+var_50], 0
0x14000fb7d  test    esi, esi
0x14000fb7f  jnz     loc_14000FC65
0x14000fb85  mov     rax, [r12]
0x14000fb89  mov     rcx, r12
0x14000fb8c  mov     rax, [rax+58h]
0x14000fb90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb95  test    rax, rax
0x14000fb98  jz      loc_14000FC5E
0x14000fb9e  mov     [rbp+4Fh+var_48], 0
0x14000fba6  mov     [rbp+4Fh+var_40], 0
0x14000fbae  mov     [rbp+4Fh+var_38], 0
0x14000fbb6  mov     rax, [r12]
0x14000fbba  mov     rcx, r12
0x14000fbbd  mov     rax, [rax+58h]
0x14000fbc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fbc6  mov     r8, rax; lpSubKey
0x14000fbc9  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14000fbd0  mov     r9d, 20119h; unsigned int
0x14000fbd6  lea     rcx, [rbp+4Fh+var_48]; this
0x14000fbda  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000fbdf  mov     esi, eax
0x14000fbe1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbe8  cmp     rcx, rbx
0x14000fbeb  jz      short loc_14000FC11
0x14000fbed  test    byte ptr [rcx+1Ch], 2
0x14000fbf1  jz      short loc_14000FC11
0x14000fbf3  cmp     byte ptr [rcx+19h], 4
0x14000fbf7  jb      short loc_14000FC11
0x14000fbf9  mov     edx, 91h
0x14000fbfe  mov     r9d, eax
0x14000fc01  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000fc08  mov     rcx, [rcx+10h]
0x14000fc0c  call    WPP_SF_d
0x14000fc11  test    esi, esi
0x14000fc13  jnz     short loc_14000FC55
0x14000fc15  lea     rdx, [rbp+4Fh+var_58]
0x14000fc19  lea     rcx, [rbp+4Fh+var_48]
0x14000fc1d  call    ?EnumSubKeys@@YAJAEAVCRegKey@ATL@@AEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@2@@Z; EnumSubKeys(ATL::CRegKey &,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)
0x14000fc22  mov     esi, eax
0x14000fc24  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc2b  cmp     rcx, rbx
0x14000fc2e  jz      short loc_14000FC55
0x14000fc30  test    byte ptr [rcx+1Ch], 2
0x14000fc34  jz      short loc_14000FC55
0x14000fc36  cmp     byte ptr [rcx+19h], 4
0x14000fc3a  jb      short loc_14000FC55
0x14000fc3c  mov     edx, 92h
0x14000fc41  mov     r9d, eax
0x14000fc44  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000fc4b  mov     rcx, [rcx+10h]
0x14000fc4f  call    WPP_SF_d
0x14000fc54  nop
0x14000fc55  lea     rcx, [rbp+4Fh+var_48]; this
0x14000fc59  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000fc5e  mov     r10, cs:WPP_GLOBAL_Control
0x14000fc65  xor     r14d, r14d
0x14000fc68  cmp     dword ptr [rbp+4Fh+var_80], r14d
0x14000fc6c  jle     loc_140010164
0x14000fc72  mov     [rbp+4Fh+Type], 0
0x14000fc79  test    r14d, r14d
0x14000fc7c  js      loc_14001021B
0x14000fc82  movsxd  r13, r14d
0x14000fc85  lea     r8, [rbp+4Fh+Type]; int *
0x14000fc89  mov     rdx, [rbp+4Fh+var_88]
0x14000fc8d  mov     rdx, [rdx+r13*8]; unsigned __int16 *
0x14000fc91  mov     rcx, r12; this
0x14000fc94  call    ?GetDeviceDisabled@CDevicesDB@@QEAAJPEBGAEAH@Z; CDevicesDB::GetDeviceDisabled(ushort const *,int &)
0x14000fc99  mov     esi, eax
0x14000fc9b  mov     r10, cs:WPP_GLOBAL_Control
0x14000fca2  cmp     r10, rbx
0x14000fca5  jz      short loc_14000FCD4
0x14000fca7  test    byte ptr [r10+1Ch], 2
0x14000fcac  jz      short loc_14000FCD4
0x14000fcae  cmp     byte ptr [r10+19h], 4
0x14000fcb3  jb      short loc_14000FCD4
0x14000fcb5  mov     edx, 93h
0x14000fcba  mov     r9d, eax
0x14000fcbd  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000fcc4  mov     rcx, [r10+10h]
0x14000fcc8  call    WPP_SF_d
0x14000fccd  mov     r10, cs:WPP_GLOBAL_Control
0x14000fcd4  test    esi, esi
0x14000fcd6  jnz     short loc_14000FD2D
0x14000fcd8  cmp     [rbp+4Fh+Type], 1
0x14000fcdc  jnz     short loc_14000FD2D
0x14000fcde  cmp     r10, rbx
0x14000fce1  jz      loc_140010157
0x14000fce7  test    byte ptr [r10+1Ch], 2
0x14000fcec  jz      loc_140010157
0x14000fcf2  cmp     byte ptr [r10+19h], 4
0x14000fcf7  jb      loc_140010157
0x14000fcfd  mov     edx, r14d
0x14000fd00  lea     rcx, [rbp+4Fh+var_88]
0x14000fd04  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x14000fd09  mov     edx, 94h
0x14000fd0e  mov     r9, [rax]
0x14000fd11  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000fd18  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd1f  mov     rcx, [rcx+10h]
0x14000fd23  call    WPP_SF_S
0x14000fd28  jmp     loc_140010150
0x14000fd2d  mov     [rbp+4Fh+arg_18], 0
0x14000fd34  cmp     r14d, dword ptr [rbp+4Fh+var_80]
0x14000fd38  jge     loc_14001021B
0x14000fd3e  lea     r9, [rbp+4Fh+arg_18]; unsigned int *
0x14000fd42  lea     r8, aDefaultauthori; "DefaultAuthorization"
0x14000fd49  mov     rdx, [rbp+4Fh+var_88]
0x14000fd4d  mov     rdx, [rdx+r13*8]; unsigned __int16 *
0x14000fd51  mov     rcx, r12; this
0x14000fd54  call    ?GetDeviceProperty@CDevicesDB@@QEAAJPEBG0AEAK@Z; CDevicesDB::GetDeviceProperty(ushort const *,ushort const *,ulong &)
0x14000fd59  test    eax, eax
0x14000fd5b  jnz     short loc_14000FD9F
0x14000fd5d  cmp     [rbp+4Fh+arg_18], 1
0x14000fd61  jnz     short loc_14000FD9F
0x14000fd63  mov     r10, cs:WPP_GLOBAL_Control
0x14000fd6a  cmp     r10, rbx
0x14000fd6d  jz      loc_140010157
0x14000fd73  test    byte ptr [r10+1Ch], 2
0x14000fd78  jz      loc_140010157
0x14000fd7e  cmp     byte ptr [r10+19h], 4
0x14000fd83  jb      loc_140010157
0x14000fd89  mov     edx, r14d
0x14000fd8c  lea     rcx, [rbp+4Fh+var_88]
0x14000fd90  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x14000fd95  mov     edx, 95h
0x14000fd9a  jmp     loc_14000FD0E
0x14000fd9f  cmp     r14d, dword ptr [rbp+4Fh+var_80]
0x14000fda3  jge     loc_14001021B
0x14000fda9  mov     rax, [rbp+4Fh+var_88]
0x14000fdad  lea     rdi, [rax+r13*8]
0x14000fdb1  xor     ebx, ebx
0x14000fdb3  mov     rax, [rbp+4Fh+arg_8]
0x14000fdb7  cmp     ebx, [rax+8]
0x14000fdba  jge     short loc_14000FE1E
0x14000fdbc  movsxd  rcx, ebx
0x14000fdbf  mov     rax, [rax]
0x14000fdc2  lea     rcx, [rax+rcx*8]
0x14000fdc6  mov     rdx, rdi
0x14000fdc9  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@0@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14000fdce  test    al, al
0x14000fdd0  jnz     short loc_14000FDD6
0x14000fdd2  inc     ebx
0x14000fdd4  jmp     short loc_14000FDB3
0x14000fdd6  cmp     ebx, 0FFFFFFFFh
0x14000fdd9  jz      short loc_14000FE1E
0x14000fddb  mov     r10, cs:WPP_GLOBAL_Control
0x14000fde2  lea     rbx, WPP_GLOBAL_Control
0x14000fde9  cmp     r10, rbx
0x14000fdec  jz      loc_140010157
0x14000fdf2  test    byte ptr [r10+1Ch], 2
0x14000fdf7  jz      loc_140010157
0x14000fdfd  cmp     byte ptr [r10+19h], 4
0x14000fe02  jb      loc_140010157
0x14000fe08  mov     edx, r14d
0x14000fe0b  lea     rcx, [rbp+4Fh+var_88]
0x14000fe0f  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x14000fe14  mov     edx, 96h
0x14000fe19  jmp     loc_14000FD0E
0x14000fe1e  cmp     qword ptr [r15+10h], 0
0x14000fe23  jz      loc_14000FF1B
0x14000fe29  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fe30  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000fe37  mov     rax, [rax+18h]
0x14000fe3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe40  add     rax, 18h
0x14000fe44  mov     [rbp+4Fh+var_68], rax
0x14000fe48  cmp     r14d, dword ptr [rbp+4Fh+var_80]
0x14000fe4c  jge     loc_1400101D9
0x14000fe52  lea     r9, [rbp+4Fh+var_68]
0x14000fe56  lea     r8, aNetworkinterfa; "NetworkInterface"
0x14000fe5d  mov     rdx, [rbp+4Fh+var_88]
0x14000fe61  mov     rdx, [rdx+r13*8]
0x14000fe65  mov     rcx, r12; this
0x14000fe68  call    ?GetDeviceProperty@CDevicesDB@@QEAAJPEBG0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CDevicesDB::GetDeviceProperty(ushort const *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x14000fe6d  mov     rbx, [rbp+4Fh+var_68]
0x14000fe71  test    eax, eax
0x14000fe73  jnz     loc_14000FF12
0x14000fe79  cmp     [rbx-10h], eax
0x14000fe7c  jz      loc_14000FF12
0x14000fe82  mov     rcx, [r15]
0x14000fe85  test    rcx, rcx
0x14000fe88  jz      short loc_14000FEB4
0x14000fe8a  mov     rax, [rcx+10h]
0x14000fe8e  mov     r9, rbx
0x14000fe91  sub     r9, rax
0x14000fe94  movzx   r8d, word ptr [rax]
0x14000fe98  movzx   edx, word ptr [rax+r9]
0x14000fe9d  sub     r8d, edx
0x14000fea0  jnz     short loc_14000FEAA
0x14000fea2  add     rax, 2
0x14000fea6  test    edx, edx
0x14000fea8  jnz     short loc_14000FE94
0x14000feaa  test    r8d, r8d
0x14000fead  jz      short loc_14000FF12
0x14000feaf  mov     rcx, [rcx]
0x14000feb2  jmp     short loc_14000FE85
0x14000feb4  mov     rax, cs:WPP_GLOBAL_Control
0x14000febb  lea     rcx, WPP_GLOBAL_Control
0x14000fec2  cmp     rax, rcx
0x14000fec5  jz      short loc_14000FF04
0x14000fec7  test    byte ptr [rax+1Ch], 2
0x14000fecb  jz      short loc_14000FF04
0x14000fecd  cmp     byte ptr [rax+19h], 4
0x14000fed1  jb      short loc_14000FF04
0x14000fed3  mov     edx, r14d
0x14000fed6  lea     rcx, [rbp+4Fh+var_88]
0x14000feda  call    ??A?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@1@H@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::operator[](int)
0x14000fedf  mov     edx, 97h
0x14000fee4  mov     [rsp+0C0h+phkResult], rbx; __int64
0x14000fee9  mov     r9, [rax]
0x14000feec  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14000fef3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fefa  mov     rcx, [rcx+10h]; LoggerHandle
0x14000fefe  call    WPP_SF_SS
0x14000ff03  nop
0x14000ff04  lea     rcx, [rbp+4Fh+var_68]
0x14000ff08  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14000ff0d  jmp     loc_140010149
0x14000ff12  lea     rcx, [rbx-18h]; this
0x14000ff16  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000ff1b  xor     edi, edi
0x14000ff1d  cmp     edi, dword ptr [rbp+4Fh+var_50]
0x14000ff20  jge     loc_140010116
0x14000ff26  xor     r15d, r15d
0x14000ff29  mov     [rbp+4Fh+var_48], r15
0x14000ff2d  mov     [rbp+4Fh+var_40], r15
0x14000ff31  mov     [rbp+4Fh+var_38], r15
0x14000ff35  mov     rax, [r12]
0x14000ff39  mov     rcx, r12
0x14000ff3c  mov     rax, [rax+58h]
0x14000ff40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff45  mov     rdx, rax
0x14000ff48  lea     rcx, [rbp+4Fh+lpSubKey]
0x14000ff4c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14000ff51  lea     rdx, asc_1400A283C; "\\"
0x14000ff58  lea     rcx, [rbp+4Fh+lpSubKey]
0x14000ff5c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x14000ff61  test    edi, edi
0x14000ff63  js      loc_140010205
0x14000ff69  movsxd  rcx, edi
0x14000ff6c  mov     rax, [rbp+4Fh+var_58]
0x14000ff70  lea     rdx, [rax+rcx*8]
0x14000ff74  lea     rcx, [rbp+4Fh+lpSubKey]
0x14000ff78  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x14000ff7d  mov     [rbp+4Fh+hKey], r15
0x14000ff81  lea     rax, [rbp+4Fh+hKey]
0x14000ff85  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14000ff8a  mov     r9d, 20119h; samDesired
0x14000ff90  xor     r8d, r8d; ulOptions
  ... truncated ...
```
