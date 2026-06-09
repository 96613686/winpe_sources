# HrCreateWrappedCOMComponent(_GUID const *,tagXW_WIZARD_TYPE,_GUID const *,void * *)

- ea: `0x18001bf44`
- end: `0x18001c193`
- name: `?HrCreateWrappedCOMComponent@@YAJPEBU_GUID@@W4tagXW_WIZARD_TYPE@@0PEAPEAX@Z`
- size: `591`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800105a0`
- `0x1800118b0`

## callees

- `0x18000ae04`
- `0x18000ae44`
- `0x18001bf44`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bf93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c01e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001bf93`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c01e`

## pseudocode

```c
__int64 __fastcall HrCreateWrappedCOMComponent(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  HRESULT v12; // eax
  int v13; // eax
  PVOID *v14; // rcx
  LPVOID v16; // [rsp+30h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-50h] BYREF
  IID rclsid; // [rsp+40h] [rbp-48h] BYREF

  ppv = 0;
  v8 = CoCreateInstance(&CLSID_CPXWizardRegistryInfo, 0, 0x401u, &IID_IPXWizardRegistryInfo, &ppv);
  if ( (v8 & 0x80000000) != 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v10 = 19;
LABEL_27:
      WPP_SF_d(v9[2], v10, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids, v8);
      return v8;
    }
    return v8;
  }
  v16 = 0;
  rclsid = 0;
  v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IID *, _QWORD))(*(_QWORD *)ppv + 88LL))(ppv, a2, &rclsid, 0);
  v8 = v11;
  if ( v11 >= 0 )
  {
    v12 = CoCreateInstance(&rclsid, 0, 0x401u, &IID_IPXWizardTypeCOMWrapper, &v16);
    v8 = v12;
    if ( v12 < 0 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_16:
        if ( v8 == -2147467262 )
        {
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
            WPP_SF_DD(v14[2], 22, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids, a2, -2147467262);
          v8 = -2147467263;
        }
        goto LABEL_24;
      }
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids, a2, v12);
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64, __int64))(*(_QWORD *)v16 + 32LL))(
              v16,
              a2,
              a1,
              a3,
              a4);
      v8 = v13;
      if ( v13 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids,
          (unsigned int)v13);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids, a2, v11);
LABEL_24:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v10 = 24;
    goto LABEL_27;
  }
  return v8;
}

```

## disassembly

```asm
0x18001bf44  push    rbx
0x18001bf46  push    rbp
0x18001bf47  push    rdi
0x18001bf48  push    r14
0x18001bf4a  push    r15
0x18001bf4c  sub     rsp, 60h
0x18001bf50  mov     rax, cs:__security_cookie
0x18001bf57  xor     rax, rsp
0x18001bf5a  mov     [rsp+88h+var_38], rax
0x18001bf5f  mov     r15, r9
0x18001bf62  mov     [rsp+88h+var_50], 0
0x18001bf6b  mov     r14, r8
0x18001bf6e  lea     rax, [rsp+88h+var_50]
0x18001bf73  mov     ebp, edx
0x18001bf75  mov     [rsp+88h+ppv], rax; ppv
0x18001bf7a  mov     rdi, rcx
0x18001bf7d  lea     r9, IID_IPXWizardRegistryInfo; riid
0x18001bf84  xor     edx, edx; pUnkOuter
0x18001bf86  lea     rcx, CLSID_CPXWizardRegistryInfo; rclsid
0x18001bf8d  mov     r8d, 401h; dwClsContext
0x18001bf93  call    cs:__imp_CoCreateInstance
0x18001bf99  mov     ebx, eax
0x18001bf9b  test    eax, eax
0x18001bf9d  jns     short loc_18001BFCA
0x18001bf9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfa6  lea     rdi, WPP_GLOBAL_Control
0x18001bfad  cmp     rcx, rdi
0x18001bfb0  jz      loc_18001C178
0x18001bfb6  test    byte ptr [rcx+1Ch], 4
0x18001bfba  jz      loc_18001C178
0x18001bfc0  mov     edx, 13h
0x18001bfc5  jmp     loc_18001C165
0x18001bfca  mov     rcx, [rsp+88h+var_50]
0x18001bfcf  lea     r8, [rsp+88h+rclsid]
0x18001bfd4  xorps   xmm0, xmm0
0x18001bfd7  mov     [rsp+88h+var_58], 0
0x18001bfe0  movups  xmmword ptr [rsp+88h+rclsid.Data1], xmm0
0x18001bfe5  xor     r9d, r9d
0x18001bfe8  mov     edx, ebp
0x18001bfea  mov     rax, [rcx]
0x18001bfed  mov     rax, [rax+58h]
0x18001bff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bff6  mov     ebx, eax
0x18001bff8  test    eax, eax
0x18001bffa  js      loc_18001C108
0x18001c000  lea     rax, [rsp+88h+var_58]
0x18001c005  xor     edx, edx; pUnkOuter
0x18001c007  lea     r9, IID_IPXWizardTypeCOMWrapper; riid
0x18001c00e  mov     [rsp+88h+ppv], rax; ppv
0x18001c013  mov     r8d, 401h; dwClsContext
0x18001c019  lea     rcx, [rsp+88h+rclsid]; rclsid
0x18001c01e  call    cs:__imp_CoCreateInstance
0x18001c024  mov     ebx, eax
0x18001c026  test    eax, eax
0x18001c028  js      short loc_18001C092
0x18001c02a  mov     rcx, [rsp+88h+var_58]
0x18001c02f  mov     r9, r14
0x18001c032  mov     r8, rdi
0x18001c035  mov     [rsp+88h+ppv], r15
0x18001c03a  mov     edx, ebp
0x18001c03c  mov     rax, [rcx]
0x18001c03f  mov     rax, [rax+20h]
0x18001c043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c048  lea     rdi, WPP_GLOBAL_Control
0x18001c04f  mov     ebx, eax
0x18001c051  test    eax, eax
0x18001c053  jns     short loc_18001C07F
0x18001c055  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c05c  cmp     rcx, rdi
0x18001c05f  jz      short loc_18001C07F
0x18001c061  test    byte ptr [rcx+1Ch], 10h
0x18001c065  jz      short loc_18001C07F
0x18001c067  mov     rcx, [rcx+10h]
0x18001c06b  lea     r8, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001c072  mov     edx, 14h
0x18001c077  mov     r9d, eax
0x18001c07a  call    WPP_SF_d
0x18001c07f  mov     rcx, [rsp+88h+var_58]
0x18001c084  mov     rax, [rcx]
0x18001c087  mov     rax, [rax+10h]
0x18001c08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c090  jmp     short loc_18001C0C7
0x18001c092  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c099  lea     rdi, WPP_GLOBAL_Control
0x18001c0a0  cmp     rcx, rdi
0x18001c0a3  jz      short loc_18001C0CE
0x18001c0a5  test    byte ptr [rcx+1Ch], 10h
0x18001c0a9  jz      short loc_18001C0CE
0x18001c0ab  mov     rcx, [rcx+10h]
0x18001c0af  lea     r8, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001c0b6  mov     edx, 15h
0x18001c0bb  mov     dword ptr [rsp+88h+ppv], eax
0x18001c0bf  mov     r9d, ebp
0x18001c0c2  call    WPP_SF_DD
0x18001c0c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0ce  cmp     ebx, 80004002h
0x18001c0d4  jnz     short loc_18001C13D
0x18001c0d6  cmp     rcx, rdi
0x18001c0d9  jz      short loc_18001C101
0x18001c0db  test    byte ptr [rcx+1Ch], 10h
0x18001c0df  jz      short loc_18001C101
0x18001c0e1  mov     rcx, [rcx+10h]
0x18001c0e5  lea     r8, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001c0ec  mov     edx, 16h
0x18001c0f1  mov     dword ptr [rsp+88h+ppv], 80004002h
0x18001c0f9  mov     r9d, ebp
0x18001c0fc  call    WPP_SF_DD
0x18001c101  mov     ebx, 80004001h
0x18001c106  jmp     short loc_18001C13D
0x18001c108  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c10f  lea     rdi, WPP_GLOBAL_Control
0x18001c116  cmp     rcx, rdi
0x18001c119  jz      short loc_18001C13D
0x18001c11b  test    byte ptr [rcx+1Ch], 10h
0x18001c11f  jz      short loc_18001C13D
0x18001c121  mov     rcx, [rcx+10h]
0x18001c125  lea     r8, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001c12c  mov     edx, 17h
0x18001c131  mov     dword ptr [rsp+88h+ppv], eax
0x18001c135  mov     r9d, ebp
0x18001c138  call    WPP_SF_DD
0x18001c13d  mov     rcx, [rsp+88h+var_50]
0x18001c142  mov     rax, [rcx]
0x18001c145  mov     rax, [rax+10h]
0x18001c149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c14e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c155  cmp     rcx, rdi
0x18001c158  jz      short loc_18001C178
0x18001c15a  test    byte ptr [rcx+1Ch], 10h
0x18001c15e  jz      short loc_18001C178
0x18001c160  mov     edx, 18h
0x18001c165  mov     rcx, [rcx+10h]
0x18001c169  lea     r8, WPP_e314a22e3b4739db2c40b7fab1625f1c_Traceguids
0x18001c170  mov     r9d, ebx
0x18001c173  call    WPP_SF_d
0x18001c178  mov     eax, ebx
0x18001c17a  mov     rcx, [rsp+88h+var_38]
0x18001c17f  xor     rcx, rsp; StackCookie
0x18001c182  call    __security_check_cookie
0x18001c187  add     rsp, 60h
0x18001c18b  pop     r15
0x18001c18d  pop     r14
0x18001c18f  pop     rdi
0x18001c190  pop     rbp
0x18001c191  pop     rbx
0x18001c192  retn
```
