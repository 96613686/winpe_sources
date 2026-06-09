# VltRemoveSettingUnit

- ea: `0x1800483f0`
- end: `0x180048628`
- name: `VltRemoveSettingUnit`
- size: `568`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180013390`
- `0x180015568`
- `0x180021b70`
- `0x180028ce0`
- `0x18002e9c0`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x1800483f0`
- `0x180048ac0`
- `0x180049ff8`
- `0x18004b17c`

## import_xrefs

- `SspiCli!GetUserNameExW` at `0x180048533`
- `SspiCli!GetUserNameExW` at `0x180048533`

## string_xrefs

- `0x180048439`: `VltRemoveSettingUnit`

## pseudocode

```c
__int64 __fastcall VltRemoveSettingUnit(__int64 a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // r8d
  struct IVaultSecurable *VaultSystemSecurable; // rax
  unsigned int v11; // edx
  unsigned int v13; // [rsp+30h] [rbp-D0h] BYREF
  ULONG nSize; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v15[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[80]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR NameBuffer[264]; // [rsp+A0h] [rbp-60h] BYREF

  v13 = 0;
  LOBYTE(v15[0]) = 0;
  v15[1] = 0;
  nSize = 257;
  FnTracer::FnTracer((FnTracer *)v16, "VltRemoveSettingUnit", &v13);
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
LABEL_9:
    v5 = 87;
    v13 = 87;
    goto LABEL_29;
  }
  if ( a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, a3);
    goto LABEL_9;
  }
  v6 = CVaultRpcImpersonate::Impersonate((CVaultRpcImpersonate *)v15, 1);
  v13 = v6;
  v5 = v6;
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 163;
LABEL_14:
      WPP_SF_d(v7[2], v8, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v6);
LABEL_15:
      v5 = v13;
    }
  }
  else
  {
    if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, v9, (unsigned int)NameBuffer, (__int64)a2, 0);
    }
    VaultSystemSecurable = GetVaultSystemSecurable();
    if ( (unsigned int)VaultAccessCheck(3, VaultSystemSecurable, 0) )
    {
      v6 = VaultDeleteRoamingCredential(a2, v11);
      v13 = v6;
      v5 = v6;
      if ( !v6 )
      {
        v5 = 0;
        goto LABEL_29;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v8 = 166;
        goto LABEL_14;
      }
    }
    else
    {
      v5 = 5;
      v13 = 5;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
        goto LABEL_15;
      }
    }
  }
LABEL_29:
  FnTracer::~FnTracer((FnTracer *)v16);
  CVaultRpcImpersonate::~CVaultRpcImpersonate(v15);
  return v5;
}

```

## disassembly

```asm
0x1800483f0  mov     [rsp-8+arg_0], rbx
0x1800483f5  push    rbp
0x1800483f6  push    rsi
0x1800483f7  push    rdi
0x1800483f8  lea     rbp, [rsp-1C0h]
0x180048400  sub     rsp, 2C0h
0x180048407  mov     rax, cs:__security_cookie
0x18004840e  xor     rax, rsp
0x180048411  mov     [rbp+1D0h+var_20], rax
0x180048418  mov     ebx, r8d
0x18004841b  mov     [rsp+2D0h+var_2A0], 0
0x180048423  mov     rsi, rdx
0x180048426  mov     [rsp+2D0h+var_298], 0
0x18004842b  lea     r8, [rsp+2D0h+var_2A0]; unsigned int *
0x180048430  mov     [rsp+2D0h+var_290], 0
0x180048439  lea     rdx, aVltremovesetti; "VltRemoveSettingUnit"
0x180048440  mov     [rsp+2D0h+nSize], 101h
0x180048448  lea     rcx, [rsp+2D0h+var_280]; this
0x18004844d  call    ??0FnTracer@@QEAA@PEADPEAK@Z; FnTracer::FnTracer(char *,ulong *)
0x180048452  test    rsi, rsi
0x180048455  jnz     short loc_180048487
0x180048457  mov     rcx, cs:WPP_GLOBAL_Control
0x18004845e  lea     rdi, WPP_GLOBAL_Control
0x180048465  cmp     rcx, rdi
0x180048468  jz      short loc_1800484BC
0x18004846a  test    byte ptr [rcx+1Ch], 2
0x18004846e  jz      short loc_1800484BC
0x180048470  mov     rcx, [rcx+10h]
0x180048474  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x18004847b  mov     edx, 0A1h
0x180048480  call    WPP_SF_
0x180048485  jmp     short loc_1800484BC
0x180048487  test    ebx, ebx
0x180048489  jz      short loc_1800484CA
0x18004848b  mov     rcx, cs:WPP_GLOBAL_Control
0x180048492  lea     rdi, WPP_GLOBAL_Control
0x180048499  cmp     rcx, rdi
0x18004849c  jz      short loc_1800484BC
0x18004849e  test    byte ptr [rcx+1Ch], 2
0x1800484a2  jz      short loc_1800484BC
0x1800484a4  mov     rcx, [rcx+10h]
0x1800484a8  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x1800484af  mov     edx, 0A2h
0x1800484b4  mov     r9d, ebx
0x1800484b7  call    WPP_SF_d
0x1800484bc  mov     ebx, 57h ; 'W'
0x1800484c1  mov     [rsp+2D0h+var_2A0], ebx
0x1800484c5  jmp     loc_1800485F0
0x1800484ca  mov     edx, 1; int
0x1800484cf  lea     rcx, [rsp+2D0h+var_298]; this
0x1800484d4  call    ?Impersonate@CVaultRpcImpersonate@@QEAAKH@Z; CVaultRpcImpersonate::Impersonate(int)
0x1800484d9  mov     [rsp+2D0h+var_2A0], eax
0x1800484dd  mov     ebx, eax
0x1800484df  test    eax, eax
0x1800484e1  jz      short loc_180048525
0x1800484e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484ea  lea     rdi, WPP_GLOBAL_Control
0x1800484f1  cmp     rcx, rdi
0x1800484f4  jz      loc_1800485F0
0x1800484fa  test    byte ptr [rcx+1Ch], 2
0x1800484fe  jz      loc_1800485F0
0x180048504  mov     edx, 0A3h
0x180048509  mov     rcx, [rcx+10h]
0x18004850d  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180048514  mov     r9d, eax
0x180048517  call    WPP_SF_d
0x18004851c  mov     ebx, [rsp+2D0h+var_2A0]
0x180048520  jmp     loc_1800485F0
0x180048525  lea     r8, [rsp+2D0h+nSize]; nSize
0x18004852a  mov     ecx, 2; NameFormat
0x18004852f  lea     rdx, [rbp+1D0h+NameBuffer]; lpNameBuffer
0x180048533  call    cs:__imp_GetUserNameExW
0x180048539  lea     rdi, WPP_GLOBAL_Control
0x180048540  test    al, al
0x180048542  jz      short loc_180048575
0x180048544  mov     rcx, cs:WPP_GLOBAL_Control
0x18004854b  cmp     rcx, rdi
0x18004854e  jz      short loc_180048575
0x180048550  test    byte ptr [rcx+1Ch], 8
0x180048554  jz      short loc_180048575
0x180048556  mov     rcx, [rcx+10h]
0x18004855a  lea     r9, [rbp+1D0h+NameBuffer]
0x18004855e  mov     edx, 0A4h
0x180048563  mov     [rsp+2D0h+var_2A8], 0
0x18004856b  mov     [rsp+2D0h+var_2B0], rsi
0x180048570  call    WPP_SF_SSD
0x180048575  call    ?GetVaultSystemSecurable@@YAPEAVIVaultSecurable@@XZ; GetVaultSystemSecurable(void)
0x18004857a  xor     r8d, r8d
0x18004857d  mov     rdx, rax
0x180048580  lea     ecx, [r8+3]
0x180048584  call    ?VaultAccessCheck@@YAHW4EVaultSecurableAction@@PEAVIVaultSecurable@@PEAH@Z; VaultAccessCheck(EVaultSecurableAction,IVaultSecurable *,int *)
0x180048589  test    eax, eax
0x18004858b  jnz     short loc_1800485C0
0x18004858d  lea     ebx, [rax+5]
0x180048590  mov     [rsp+2D0h+var_2A0], ebx
0x180048594  mov     rcx, cs:WPP_GLOBAL_Control
0x18004859b  cmp     rcx, rdi
0x18004859e  jz      short loc_1800485F0
0x1800485a0  test    byte ptr [rcx+1Ch], 2
0x1800485a4  jz      short loc_1800485F0
0x1800485a6  mov     rcx, [rcx+10h]
0x1800485aa  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x1800485b1  mov     edx, 0A5h
0x1800485b6  call    WPP_SF_
0x1800485bb  jmp     loc_18004851C
0x1800485c0  mov     rcx, rsi; unsigned __int16 *
0x1800485c3  call    ?VaultDeleteRoamingCredential@@YAKPEBGK@Z; VaultDeleteRoamingCredential(ushort const *,ulong)
0x1800485c8  mov     [rsp+2D0h+var_2A0], eax
0x1800485cc  mov     ebx, eax
0x1800485ce  test    eax, eax
0x1800485d0  jz      short loc_1800485EE
0x1800485d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800485d9  cmp     rcx, rdi
0x1800485dc  jz      short loc_1800485F0
0x1800485de  test    byte ptr [rcx+1Ch], 2
0x1800485e2  jz      short loc_1800485F0
0x1800485e4  mov     edx, 0A6h
0x1800485e9  jmp     loc_180048509
0x1800485ee  xor     ebx, ebx
0x1800485f0  lea     rcx, [rsp+2D0h+var_280]; this
0x1800485f5  call    ??1FnTracer@@QEAA@XZ; FnTracer::~FnTracer(void)
0x1800485fa  lea     rcx, [rsp+2D0h+var_298]; this
0x1800485ff  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180048604  mov     eax, ebx
0x180048606  mov     rcx, [rbp+1D0h+var_20]
0x18004860d  xor     rcx, rsp; StackCookie
0x180048610  call    __security_check_cookie
0x180048615  mov     rbx, [rsp+2D0h+arg_0]
0x18004861d  add     rsp, 2C0h
0x180048624  pop     rdi
0x180048625  pop     rsi
0x180048626  pop     rbp
0x180048627  retn
```
