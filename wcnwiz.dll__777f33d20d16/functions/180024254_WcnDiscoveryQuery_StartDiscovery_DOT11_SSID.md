# WcnDiscoveryQuery::StartDiscovery(_DOT11_SSID *)

- ea: `0x180024254`
- end: `0x180024410`
- name: `?StartDiscovery@WcnDiscoveryQuery@@QEAAJPEAU_DOT11_SSID@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(WcnDiscoveryQuery *__hidden this, struct _DOT11_SSID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ff20`

## callees

- `0x180001820`
- `0x180002981`
- `0x18000e1dc`
- `0x180019fc0`
- `0x18001ec74`
- `0x18001edf4`
- `0x180024254`
- `0x180024f30`
- `0x18002de1c`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024333`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024333`

## pseudocode

```c
HRESULT __fastcall WcnDiscoveryQuery::StartDiscovery(WcnDiscoveryQuery *this, struct _DOT11_SSID *a2, unsigned int a3)
{
  _QWORD *v5; // rdi
  size_t uSSIDLength; // r8
  unsigned int Indent; // eax
  _QWORD *v8; // rdi
  HRESULT result; // eax
  int v10; // esi
  unsigned int v11; // eax
  __int64 v12; // r10
  unsigned int v13; // edx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v17[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  unsigned __int8 v19[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[72]; // [rsp+80h] [rbp-80h] BYREF

  *(struct _DOT11_SSID *)((char *)this + 16) = *a2;
  v5 = WPP_GLOBAL_Control;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000) != 0 )
  {
    uSSIDLength = a2->uSSIDLength;
    v18 = 0;
    memset(v17, 0, sizeof(v17));
    memcpy_0(v17, a2->ucSSID, uSSIDLength);
    if ( v5 != &WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 5u )
    {
      Indent = (unsigned int)GetIndent(0);
      WPP_SF_ss(v5[2], 10, (unsigned int)WPP_f1914741326232246567aea6d76b05ac_Traceguids, Indent, (__int64)v17);
    }
  }
  v8 = (_QWORD *)((char *)this + 56);
  if ( *((_QWORD *)this + 7) )
    goto LABEL_12;
  Microsoft::WRL::ComPtr<IWCNDiscoveryProvider>::InternalRelease((char *)this + 56);
  result = CoCreateInstance(
             &GUID_c100bea3_d33a_4a4b_bf23_bbef4663d017,
             0,
             1u,
             &GUID_c100be9a_d33a_4a4b_bf23_bbef4663d017,
             (LPVOID *)this + 7);
  if ( result < 0 )
    return result;
  v10 = (*(__int64 (__fastcall **)(_QWORD, WcnDiscoveryQuery *))(*(_QWORD *)*v8 + 24LL))(*v8, this);
  if ( v10 >= 0 )
  {
LABEL_12:
    result = WcnStringBlobToHex(a2->uSSIDLength, a2->ucSSID, a3, v20);
    if ( result >= 0 )
    {
      v16 = 0;
      result = WcnStringHexToBlob(v20, v13, v19, &v16);
      if ( result >= 0 )
      {
        v14 = *v8;
        v15 = v16;
        *((_BYTE *)this + 72) = 1;
        return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int8 *, _DWORD))(*(_QWORD *)v14 + 40LL))(
                 v14,
                 0,
                 v15,
                 v19,
                 0);
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = (unsigned int)GetIndent(0);
      WPP_SF_sd(*(_QWORD *)(v12 + 16), 11, (unsigned int)WPP_f1914741326232246567aea6d76b05ac_Traceguids, v11, v10);
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180024254  mov     [rsp-8+arg_10], rbx
0x180024259  push    rbp
0x18002425a  push    rsi
0x18002425b  push    rdi
0x18002425c  push    r12
0x18002425e  push    r14
0x180024260  lea     rbp, [rsp-20h]
0x180024265  sub     rsp, 120h
0x18002426c  mov     rax, cs:__security_cookie
0x180024273  xor     rax, rsp
0x180024276  mov     [rbp+40h+var_30], rax
0x18002427a  movups  xmm0, xmmword ptr [rdx]
0x18002427d  mov     rbx, rdx
0x180024280  lea     r12, WPP_GLOBAL_Control
0x180024287  mov     r14, rcx
0x18002428a  movups  xmmword ptr [rcx+10h], xmm0
0x18002428e  movups  xmm1, xmmword ptr [rdx+10h]
0x180024292  movups  xmmword ptr [rcx+20h], xmm1
0x180024296  mov     eax, [rdx+20h]
0x180024299  mov     [rcx+30h], eax
0x18002429c  mov     rdi, cs:WPP_GLOBAL_Control
0x1800242a3  test    dword ptr [rdi+1Ch], 20000h
0x1800242aa  jz      short loc_180024304
0x1800242ac  mov     r8d, [rdx]; Size
0x1800242af  lea     rcx, [rsp+140h+var_108]; void *
0x1800242b4  xorps   xmm0, xmm0
0x1800242b7  xor     eax, eax
0x1800242b9  add     rdx, 4; Src
0x1800242bd  mov     [rsp+140h+var_E8], al
0x1800242c1  movups  [rsp+140h+var_108], xmm0
0x1800242c6  movups  [rsp+140h+var_F8], xmm0
0x1800242cb  call    memcpy_0
0x1800242d0  cmp     rdi, r12
0x1800242d3  jz      short loc_180024304
0x1800242d5  cmp     byte ptr [rdi+19h], 5
0x1800242d9  jb      short loc_180024304
0x1800242db  xor     ecx, ecx; int
0x1800242dd  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800242e2  lea     rcx, [rsp+140h+var_108]
0x1800242e7  mov     edx, 0Ah
0x1800242ec  mov     [rsp+140h+ppv], rcx
0x1800242f1  lea     r8, WPP_f1914741326232246567aea6d76b05ac_Traceguids
0x1800242f8  mov     rcx, [rdi+10h]
0x1800242fc  mov     r9, rax
0x1800242ff  call    WPP_SF_ss
0x180024304  lea     rdi, [r14+38h]
0x180024308  cmp     qword ptr [rdi], 0
0x18002430c  jnz     loc_180024393
0x180024312  mov     rcx, rdi
0x180024315  call    ?InternalRelease@?$ComPtr@UIWCNDiscoveryProvider@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWCNDiscoveryProvider>::InternalRelease(void)
0x18002431a  xor     edx, edx; pUnkOuter
0x18002431c  mov     [rsp+140h+ppv], rdi; ppv
0x180024321  lea     r9, _GUID_c100be9a_d33a_4a4b_bf23_bbef4663d017; riid
0x180024328  lea     rcx, _GUID_c100bea3_d33a_4a4b_bf23_bbef4663d017; rclsid
0x18002432f  lea     r8d, [rdx+1]; dwClsContext
0x180024333  call    cs:__imp_CoCreateInstance
0x180024339  test    eax, eax
0x18002433b  js      loc_1800243ED
0x180024341  mov     rcx, [rdi]
0x180024344  mov     rdx, r14
0x180024347  mov     rax, [rcx]
0x18002434a  mov     rax, [rax+18h]
0x18002434e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024353  mov     esi, eax
0x180024355  test    eax, eax
0x180024357  jns     short loc_180024393
0x180024359  mov     r10, cs:WPP_GLOBAL_Control
0x180024360  cmp     r10, r12
0x180024363  jz      short loc_18002438F
0x180024365  cmp     byte ptr [r10+19h], 2
0x18002436a  jb      short loc_18002438F
0x18002436c  xor     ecx, ecx; int
0x18002436e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180024373  mov     rcx, [r10+10h]
0x180024377  lea     r8, WPP_f1914741326232246567aea6d76b05ac_Traceguids
0x18002437e  mov     edx, 0Bh
0x180024383  mov     dword ptr [rsp+140h+ppv], esi
0x180024387  mov     r9, rax
0x18002438a  call    WPP_SF_sd
0x18002438f  mov     eax, esi
0x180024391  jmp     short loc_1800243ED
0x180024393  mov     ecx, [rbx]; unsigned int
0x180024395  lea     rdx, [rbx+4]; unsigned __int8 *
0x180024399  lea     r9, [rbp+40h+var_C0]; unsigned __int16 *
0x18002439d  call    ?WcnStringBlobToHex@@YAJKPEBEKPEAG@Z; WcnStringBlobToHex(ulong,uchar const *,ulong,ushort *)
0x1800243a2  test    eax, eax
0x1800243a4  js      short loc_1800243ED
0x1800243a6  lea     r9, [rsp+140h+var_110]; unsigned int *
0x1800243ab  mov     [rsp+140h+var_110], 0
0x1800243b3  lea     r8, [rsp+140h+var_E0]; unsigned __int8 *
0x1800243b8  lea     rcx, [rbp+40h+var_C0]; unsigned __int16 *
0x1800243bc  call    ?WcnStringHexToBlob@@YAJPEBGKPEAEPEAK@Z; WcnStringHexToBlob(ushort const *,ulong,uchar *,ulong *)
0x1800243c1  test    eax, eax
0x1800243c3  js      short loc_1800243ED
0x1800243c5  mov     rcx, [rdi]
0x1800243c8  lea     r9, [rsp+140h+var_E0]
0x1800243cd  mov     r8d, [rsp+140h+var_110]
0x1800243d2  xor     edx, edx
0x1800243d4  mov     byte ptr [r14+48h], 1
0x1800243d9  mov     dword ptr [rsp+140h+ppv], 0
0x1800243e1  mov     rax, [rcx]
0x1800243e4  mov     rax, [rax+28h]
0x1800243e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243ed  mov     rcx, [rbp+40h+var_30]
0x1800243f1  xor     rcx, rsp; StackCookie
0x1800243f4  call    __security_check_cookie
0x1800243f9  mov     rbx, [rsp+140h+arg_10]
0x180024401  add     rsp, 120h
0x180024408  pop     r14
0x18002440a  pop     r12
0x18002440c  pop     rdi
0x18002440d  pop     rsi
0x18002440e  pop     rbp
0x18002440f  retn
```
