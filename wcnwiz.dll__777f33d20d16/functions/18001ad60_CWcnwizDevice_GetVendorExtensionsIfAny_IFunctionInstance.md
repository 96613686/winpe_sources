# CWcnwizDevice::GetVendorExtensionsIfAny(IFunctionInstance *)

- ea: `0x18001ad60`
- end: `0x18001af1c`
- name: `?GetVendorExtensionsIfAny@CWcnwizDevice@@AEAAXPEAUIFunctionInstance@@@Z`
- size: `444`
- prototype: `void __fastcall(CWcnwizDevice *__hidden this, struct IFunctionInstance *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001af24`

## callees

- `0x180001820`
- `0x180003abc`
- `0x18000e19c`
- `0x18000e1dc`
- `0x18001ad60`
- `0x18001b3c8`
- `0x18002de1c`
- `0x180031010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CWcnwizDevice::GetVendorExtensionsIfAny(CWcnwizDevice *this, struct IFunctionInstance *a2)
{
  int v3; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // r10
  int v8; // edx
  int v9; // r8d
  char v10; // r11
  unsigned int Indent; // eax
  __int64 v12; // r10
  char v13; // r11
  _WORD v14[2]; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v16; // [rsp+38h] [rbp-28h] BYREF
  __int128 v17; // [rsp+40h] [rbp-20h] BYREF

  v17 = 0;
  v16 = 0;
  v14[0] = 0;
  v15 = 0;
  v3 = ((__int64 (__fastcall *)(struct IFunctionInstance *, SID *, GUID *, __int64 *))a2->lpVtbl->QueryService)(
         a2,
         &SID_WcnProvider,
         &GUID_c100be9c_d33a_4a4b_bf23_bbef4663d017,
         &v16);
  if ( v3 >= 0 )
  {
    HIDWORD(v17) = 1;
    *(_QWORD *)((char *)&v17 + 4) = 8193;
    LODWORD(v17) = 311;
    v3 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _WORD *, int *))(*(_QWORD *)v16 + 80LL))(
           v16,
           &v17,
           2,
           v14,
           &v15);
    if ( v3 >= 0 )
    {
      if ( v15 == 2 )
      {
        *((_DWORD *)this + 24) = (unsigned __int16)__ROR2__(v14[0], 8);
        *((_BYTE *)this + 92) = 1;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          Indent = (unsigned int)GetIndent(0);
          WPP_SF_sd(
            *(_QWORD *)(v12 + 16),
            22,
            (unsigned int)WPP_510faab3c43a30fab228fe98e5d76271_Traceguids,
            Indent,
            v13);
        }
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v6 = (unsigned int)GetIndent(0);
        WPP_SF_sDP(*(_QWORD *)(v7 + 16), v8, v9, v6, v10);
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 20;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 19;
LABEL_5:
      WPP_SF_d(v4[2], v5, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids, (unsigned int)v3);
    }
  }
  ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(&v16);
}

```

## disassembly

```asm
0x18001ad60  mov     [rsp-8+arg_10], rbx
0x18001ad65  push    rbp
0x18001ad66  mov     rbp, rsp
0x18001ad69  sub     rsp, 60h
0x18001ad6d  mov     rax, cs:__security_cookie
0x18001ad74  xor     rax, rsp
0x18001ad77  mov     [rbp+var_10], rax
0x18001ad7b  mov     r10, rdx
0x18001ad7e  mov     rbx, rcx
0x18001ad81  xorps   xmm0, xmm0
0x18001ad84  movups  [rbp+var_20], xmm0
0x18001ad88  mov     [rbp+var_28], 0
0x18001ad90  xor     eax, eax
0x18001ad92  mov     [rbp+var_30], ax
0x18001ad96  mov     [rbp+var_2C], eax
0x18001ad99  mov     rax, [rdx]
0x18001ad9c  lea     r9, [rbp+var_28]
0x18001ada0  lea     r8, _GUID_c100be9c_d33a_4a4b_bf23_bbef4663d017
0x18001ada7  lea     rdx, SID_WcnProvider
0x18001adae  mov     rcx, r10
0x18001adb1  mov     rax, [rax+18h]
0x18001adb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001adba  test    eax, eax
0x18001adbc  jns     short loc_18001ADFC
0x18001adbe  lea     rdx, WPP_GLOBAL_Control
0x18001adc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001adcc  cmp     rcx, rdx
0x18001adcf  jz      loc_18001AEF9
0x18001add5  cmp     byte ptr [rcx+19h], 2
0x18001add9  jb      loc_18001AEF9
0x18001addf  mov     edx, 13h
0x18001ade4  mov     r9d, eax
0x18001ade7  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001adee  mov     rcx, [rcx+10h]
0x18001adf2  call    WPP_SF_d
0x18001adf7  jmp     loc_18001AEF9
0x18001adfc  mov     dword ptr [rbp+var_20+0Ch], 1
0x18001ae03  mov     qword ptr [rbp+var_20+4], 2001h
0x18001ae0b  mov     dword ptr [rbp+var_20], 137h
0x18001ae12  mov     rcx, [rbp+var_28]
0x18001ae16  mov     rax, [rcx]
0x18001ae19  lea     rdx, [rbp+var_2C]
0x18001ae1d  mov     [rsp+60h+var_40], rdx
0x18001ae22  lea     r9, [rbp+var_30]
0x18001ae26  mov     r8d, 2
0x18001ae2c  lea     rdx, [rbp+var_20]
0x18001ae30  mov     rax, [rax+50h]
0x18001ae34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae39  test    eax, eax
0x18001ae3b  jns     short loc_18001AE68
0x18001ae3d  lea     rdx, WPP_GLOBAL_Control
0x18001ae44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae4b  cmp     rcx, rdx
0x18001ae4e  jz      loc_18001AEF9
0x18001ae54  cmp     byte ptr [rcx+19h], 2
0x18001ae58  jb      loc_18001AEF9
0x18001ae5e  mov     edx, 14h
0x18001ae63  jmp     loc_18001ADE4
0x18001ae68  mov     r11d, [rbp+var_2C]
0x18001ae6c  cmp     r11d, 2
0x18001ae70  jz      short loc_18001AEA6
0x18001ae72  lea     rdx, WPP_GLOBAL_Control
0x18001ae79  mov     r10, cs:WPP_GLOBAL_Control
0x18001ae80  cmp     r10, rdx
0x18001ae83  jz      short loc_18001AEF9
0x18001ae85  cmp     byte ptr [r10+19h], 3
0x18001ae8a  jb      short loc_18001AEF9
0x18001ae8c  xor     ecx, ecx; int
0x18001ae8e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001ae93  mov     dword ptr [rsp+60h+var_40], r11d
0x18001ae98  mov     r9, rax
0x18001ae9b  mov     rcx, [r10+10h]
0x18001ae9f  call    WPP_SF_sDP
0x18001aea4  jmp     short loc_18001AEF9
0x18001aea6  movzx   eax, [rbp+var_30]
0x18001aeaa  ror     ax, 8
0x18001aeae  movzx   r11d, ax
0x18001aeb2  mov     [rbx+60h], r11d
0x18001aeb6  mov     byte ptr [rbx+5Ch], 1
0x18001aeba  lea     rdx, WPP_GLOBAL_Control
0x18001aec1  mov     r10, cs:WPP_GLOBAL_Control
0x18001aec8  cmp     r10, rdx
0x18001aecb  jz      short loc_18001AEF9
0x18001aecd  cmp     byte ptr [r10+19h], 5
0x18001aed2  jb      short loc_18001AEF9
0x18001aed4  xor     ecx, ecx; int
0x18001aed6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001aedb  mov     edx, 16h
0x18001aee0  mov     dword ptr [rsp+60h+var_40], r11d
0x18001aee5  mov     r9, rax
0x18001aee8  lea     r8, WPP_510faab3c43a30fab228fe98e5d76271_Traceguids
0x18001aeef  mov     rcx, [r10+10h]
0x18001aef3  call    WPP_SF_sd
0x18001aef8  nop
0x18001aef9  lea     rcx, [rbp+var_28]
0x18001aefd  call    ??1?$CComPtrBase@UIWCNDevicePrivate@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWCNDevicePrivate>::~CComPtrBase<IWCNDevicePrivate>(void)
0x18001af02  mov     rcx, [rbp+var_10]
0x18001af06  xor     rcx, rsp; StackCookie
0x18001af09  call    __security_check_cookie
0x18001af0e  mov     rbx, [rsp+60h+arg_10]
0x18001af16  add     rsp, 60h
0x18001af1a  pop     rbp
0x18001af1b  retn
```
