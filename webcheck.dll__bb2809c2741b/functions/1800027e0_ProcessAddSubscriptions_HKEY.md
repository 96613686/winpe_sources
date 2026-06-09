# ProcessAddSubscriptions(HKEY__ *)

- ea: `0x1800027e0`
- end: `0x180002afe`
- name: `?ProcessAddSubscriptions@@YAJPEAUHKEY__@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800024f4`
- `0x180002614`
- `0x1800026e4`
- `0x18000272c`
- `0x18000279c`
- `0x1800027e0`
- `0x18000cc84`
- `0x18002924e`
- `0x180029280`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800029ae`
- `ole32!CoCreateInstance` at `0x1800029ae`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a67`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002aaa`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a67`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180002a9c`
- `OLEAUT32!__imp_SysFreeString` at `0x180002aaa`

## pseudocode

```c
__int64 __fastcall ProcessAddSubscriptions(HKEY hKey)
{
  int Value; // eax
  unsigned __int16 *v3; // r14
  int v4; // r13d
  OLECHAR *v5; // rdi
  OLECHAR *v6; // rbx
  int v7; // eax
  __int64 v8; // r8
  unsigned int v9; // r9d
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  BSTR ppv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v13; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v14; // [rsp+58h] [rbp-A8h] BYREF
  BSTR v15; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+70h] [rbp-90h]
  BSTR v18; // [rsp+78h] [rbp-88h] BYREF
  HKEY v19; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+88h] [rbp-78h]
  int v21; // [rsp+90h] [rbp-70h] BYREF
  _DWORD v22[17]; // [rsp+94h] [rbp-6Ch] BYREF
  OLECHAR *v23; // [rsp+D8h] [rbp-28h]
  OLECHAR *v24; // [rsp+E0h] [rbp-20h]
  BSTR bstrString[2]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  v19 = hKey;
  v20 = 0;
  while ( !CRegKey::Next((CRegKey *)&v19, SubKey) )
  {
    phkResult = 0;
    v17 = 0;
    CRegKey::OpenForRead(&phkResult, hKey, SubKey);
    bstrString[0] = 0;
    v15 = 0;
    v18 = 0;
    ppv = 0;
    v14 = 0;
    v11 = 0;
    v13 = 0;
    CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"URL", bstrString);
    CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"Title", &v15);
    CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"ScheduleGroup", &v18);
    CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"Username", &ppv);
    CRegKey::GetBSTRValue((CRegKey *)&phkResult, L"Password", &v14);
    Value = CRegKey::GetValue((CRegKey *)&phkResult, L"Synchronize", &v13);
    v3 = bstrString[0];
    v4 = Value;
    v5 = ppv;
    v6 = v14;
    if ( bstrString[0] )
    {
      if ( v15 && v18 && (int)CRegKey::GetValue((CRegKey *)&phkResult, L"SubscriptionType", &v11) >= 0 )
      {
        memset_0(v22, 0, 0x6Cu);
        v21 = 112;
        v22[0] = 1;
        v7 = 1;
        if ( v5 && v6 )
        {
          v7 = 97;
          v23 = v5;
          v22[0] = 97;
          v24 = v6;
        }
        if ( v11 == 1 || v11 == 4 )
        {
          v22[15] = 0;
          v22[0] = v7 | 0x800;
        }
        if ( v4 >= 0 )
        {
          ppv = 0;
          if ( CoCreateInstance(&CLSID_SubscriptionMgr, 0, 1u, &IID_ISubscriptionMgr2, (LPVOID *)&ppv) >= 0 )
          {
            (*(void (__fastcall **)(BSTR, _QWORD, unsigned __int16 *, BSTR, int, unsigned int, int *))(*(_QWORD *)ppv + 80LL))(
              ppv,
              0,
              v3,
              v15,
              4,
              v11,
              &v21);
            if ( v13 )
            {
              LODWORD(v14) = 0;
              *(_OWORD *)bstrString = 0;
              if ( (*(int (__fastcall **)(BSTR, unsigned __int16 *, BSTR *))(*(_QWORD *)ppv + 48LL))(ppv, v3, &v14) >= 0
                && (_DWORD)v14
                && (int)ReadCookieFromInetDB(v3, (LPIID)bstrString, v8, v9) >= 0 )
              {
                (*(void (__fastcall **)(BSTR, __int64, __int64, BSTR *))(*(_QWORD *)ppv + 120LL))(ppv, 1, 1, bstrString);
              }
            }
            (*(void (__fastcall **)(BSTR))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
      }
      SysFreeString(v3);
    }
    if ( v15 )
      SysFreeString(v15);
    if ( v18 )
      SysFreeString(v18);
    if ( v5 )
      SysFreeString(v5);
    if ( v6 )
      SysFreeString(v6);
    CRegKey::~CRegKey((CRegKey *)&phkResult);
  }
  v19 = 0;
  CRegKey::~CRegKey((CRegKey *)&v19);
  return 0;
}

```

## disassembly

```asm
0x1800027e0  push    rbp
0x1800027e2  push    rbx
0x1800027e3  push    rdi
0x1800027e4  push    r12
0x1800027e6  push    r13
0x1800027e8  push    r14
0x1800027ea  lea     rbp, [rsp-238h]
0x1800027f2  sub     rsp, 338h
0x1800027f9  mov     rax, cs:__security_cookie
0x180002800  xor     rax, rsp
0x180002803  mov     [rbp+260h+var_40], rax
0x18000280a  xor     r14d, r14d
0x18000280d  mov     [rbp+260h+var_2E0], rcx
0x180002811  mov     [rbp+260h+var_2D8], r14d
0x180002815  mov     r12, rcx
0x180002818  jmp     loc_180002ABA
0x18000281d  lea     r8, [rbp+260h+SubKey]; lpSubKey
0x180002821  mov     [rsp+360h+phkResult], r14
0x180002826  mov     rdx, r12; hKey
0x180002829  mov     [rsp+360h+var_2F0], r14d
0x18000282e  lea     rcx, [rsp+360h+phkResult]; phkResult
0x180002833  call    ?OpenForRead@CRegKey@@QEAAJPEAUHKEY__@@PEBG@Z; CRegKey::OpenForRead(HKEY__ *,ushort const *)
0x180002838  lea     r8, [rbp+260h+bstrString]; unsigned __int16 **
0x18000283c  mov     [rbp+260h+bstrString], r14
0x180002840  lea     rdx, aUrl_1; "URL"
0x180002847  mov     [rsp+360h+var_300], r14
0x18000284c  lea     rcx, [rsp+360h+phkResult]; this
0x180002851  mov     [rsp+360h+var_2E8], r14
0x180002856  mov     [rsp+360h+var_318], r14
0x18000285b  mov     [rsp+360h+var_308], r14
0x180002860  mov     [rsp+360h+var_320], r14d
0x180002865  mov     [rsp+360h+var_310], r14d
0x18000286a  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x18000286f  lea     r8, [rsp+360h+var_300]; unsigned __int16 **
0x180002874  lea     rdx, aTitle; "Title"
0x18000287b  lea     rcx, [rsp+360h+phkResult]; this
0x180002880  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x180002885  lea     r8, [rsp+360h+var_2E8]; unsigned __int16 **
0x18000288a  lea     rdx, aSchedulegroup; "ScheduleGroup"
0x180002891  lea     rcx, [rsp+360h+phkResult]; this
0x180002896  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x18000289b  lea     r8, [rsp+360h+var_318]; unsigned __int16 **
0x1800028a0  lea     rdx, aUsername; "Username"
0x1800028a7  lea     rcx, [rsp+360h+phkResult]; this
0x1800028ac  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x1800028b1  lea     r8, [rsp+360h+var_308]; unsigned __int16 **
0x1800028b6  lea     rdx, aPassword; "Password"
0x1800028bd  lea     rcx, [rsp+360h+phkResult]; this
0x1800028c2  call    ?GetBSTRValue@CRegKey@@QEAAJPEBGPEAPEAG@Z; CRegKey::GetBSTRValue(ushort const *,ushort * *)
0x1800028c7  lea     r8, [rsp+360h+var_310]; unsigned int *
0x1800028cc  lea     rdx, aSynchronize; "Synchronize"
0x1800028d3  lea     rcx, [rsp+360h+phkResult]; this
0x1800028d8  call    ?GetValue@CRegKey@@QEAAJPEBGPEAK@Z; CRegKey::GetValue(ushort const *,ulong *)
0x1800028dd  mov     r14, [rbp+260h+bstrString]
0x1800028e1  mov     r13d, eax
0x1800028e4  mov     rdi, [rsp+360h+var_318]
0x1800028e9  mov     rbx, [rsp+360h+var_308]
0x1800028ee  test    r14, r14
0x1800028f1  jz      loc_180002A6D
0x1800028f7  cmp     [rsp+360h+var_300], 0
0x1800028fd  jz      loc_180002A64
0x180002903  cmp     [rsp+360h+var_2E8], 0
0x180002909  jz      loc_180002A64
0x18000290f  lea     r8, [rsp+360h+var_320]; unsigned int *
0x180002914  lea     rdx, aSubscriptionty; "SubscriptionType"
0x18000291b  lea     rcx, [rsp+360h+phkResult]; this
0x180002920  call    ?GetValue@CRegKey@@QEAAJPEBGPEAK@Z; CRegKey::GetValue(ushort const *,ulong *)
0x180002925  test    eax, eax
0x180002927  js      loc_180002A64
0x18000292d  xor     edx, edx; Val
0x18000292f  lea     rcx, [rbp+260h+var_2CC]; void *
0x180002933  lea     r8d, [rdx+6Ch]; Size
0x180002937  call    memset_0
0x18000293c  mov     [rbp+260h+var_2D0], 70h ; 'p'
0x180002943  mov     ecx, 1
0x180002948  mov     [rbp+260h+var_2CC], ecx
0x18000294b  mov     eax, ecx
0x18000294d  test    rdi, rdi
0x180002950  jz      short loc_180002965
0x180002952  test    rbx, rbx
0x180002955  jz      short loc_180002965
0x180002957  lea     eax, [rcx+60h]
0x18000295a  mov     [rbp+260h+var_288], rdi
0x18000295e  mov     [rbp+260h+var_2CC], eax
0x180002961  mov     [rbp+260h+var_280], rbx
0x180002965  cmp     [rsp+360h+var_320], ecx
0x180002969  jz      short loc_180002972
0x18000296b  cmp     [rsp+360h+var_320], 4
0x180002970  jnz     short loc_180002980
0x180002972  bts     eax, 0Bh
0x180002976  mov     [rbp+260h+var_290], 0
0x18000297d  mov     [rbp+260h+var_2CC], eax
0x180002980  test    r13d, r13d
0x180002983  js      loc_180002A64
0x180002989  lea     rax, [rsp+360h+var_318]
0x18000298e  mov     r8d, ecx; dwClsContext
0x180002991  xor     r13d, r13d
0x180002994  mov     [rsp+360h+ppv], rax; ppv
0x180002999  lea     rcx, CLSID_SubscriptionMgr; rclsid
0x1800029a0  mov     [rsp+360h+var_318], r13
0x1800029a5  lea     r9, IID_ISubscriptionMgr2; riid
0x1800029ac  xor     edx, edx; pUnkOuter
0x1800029ae  call    cs:__imp_CoCreateInstance
0x1800029b4  test    eax, eax
0x1800029b6  js      loc_180002A64
0x1800029bc  mov     rcx, [rsp+360h+var_318]
0x1800029c1  lea     rdx, [rbp+260h+var_2D0]
0x1800029c5  mov     r9, [rsp+360h+var_300]
0x1800029ca  mov     r8, r14
0x1800029cd  mov     [rsp+360h+var_330], rdx
0x1800029d2  mov     edx, [rsp+360h+var_320]
0x1800029d6  mov     rax, [rcx]
0x1800029d9  mov     [rsp+360h+var_338], edx
0x1800029dd  xor     edx, edx
0x1800029df  mov     dword ptr [rsp+360h+ppv], 4
0x1800029e7  mov     rax, [rax+50h]
0x1800029eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f0  cmp     [rsp+360h+var_310], r13d
0x1800029f5  jz      short loc_180002A53
0x1800029f7  mov     rcx, [rsp+360h+var_318]
0x1800029fc  lea     r8, [rsp+360h+var_308]
0x180002a01  xorps   xmm0, xmm0
0x180002a04  mov     dword ptr [rsp+360h+var_308], r13d
0x180002a09  movups  xmmword ptr [rbp+260h+bstrString], xmm0
0x180002a0d  mov     rdx, r14
0x180002a10  mov     rax, [rcx]
0x180002a13  mov     rax, [rax+30h]
0x180002a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1c  test    eax, eax
0x180002a1e  js      short loc_180002A53
0x180002a20  cmp     dword ptr [rsp+360h+var_308], r13d
0x180002a25  jz      short loc_180002A53
0x180002a27  lea     rdx, [rbp+260h+bstrString]; lpiid
0x180002a2b  mov     rcx, r14; unsigned __int16 *
0x180002a2e  call    ?ReadCookieFromInetDB@@YAJPEBGPEAU_GUID@@@Z; ReadCookieFromInetDB(ushort const *,_GUID *)
0x180002a33  test    eax, eax
0x180002a35  js      short loc_180002A53
0x180002a37  mov     rcx, [rsp+360h+var_318]
0x180002a3c  lea     edx, [r13+1]
0x180002a40  lea     r9, [rbp+260h+bstrString]
0x180002a44  mov     r8d, edx
0x180002a47  mov     rax, [rcx]
0x180002a4a  mov     rax, [rax+78h]
0x180002a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a53  mov     rcx, [rsp+360h+var_318]
0x180002a58  mov     rax, [rcx]
0x180002a5b  mov     rax, [rax+10h]
0x180002a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a64  mov     rcx, r14; bstrString
0x180002a67  call    cs:__imp_SysFreeString
0x180002a6d  xor     r14d, r14d
0x180002a70  cmp     [rsp+360h+var_300], r14
0x180002a75  jz      short loc_180002A82
0x180002a77  mov     rcx, [rsp+360h+var_300]; bstrString
0x180002a7c  call    cs:__imp_SysFreeString
0x180002a82  cmp     [rsp+360h+var_2E8], r14
0x180002a87  jz      short loc_180002A94
0x180002a89  mov     rcx, [rsp+360h+var_2E8]; bstrString
0x180002a8e  call    cs:__imp_SysFreeString
0x180002a94  test    rdi, rdi
0x180002a97  jz      short loc_180002AA2
0x180002a99  mov     rcx, rdi; bstrString
0x180002a9c  call    cs:__imp_SysFreeString
0x180002aa2  test    rbx, rbx
0x180002aa5  jz      short loc_180002AB0
0x180002aa7  mov     rcx, rbx; bstrString
0x180002aaa  call    cs:__imp_SysFreeString
0x180002ab0  lea     rcx, [rsp+360h+phkResult]; this
0x180002ab5  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002aba  lea     rdx, [rbp+260h+SubKey]; unsigned __int16 *
0x180002abe  lea     rcx, [rbp+260h+var_2E0]; this
0x180002ac2  call    ?Next@CRegKey@@QEAAJPEAG@Z; CRegKey::Next(ushort *)
0x180002ac7  test    eax, eax
0x180002ac9  jz      loc_18000281D
0x180002acf  lea     rcx, [rbp+260h+var_2E0]; this
0x180002ad3  mov     [rbp+260h+var_2E0], r14
0x180002ad7  call    ??1CRegKey@@QEAA@XZ; CRegKey::~CRegKey(void)
0x180002adc  xor     eax, eax
0x180002ade  mov     rcx, [rbp+260h+var_40]
0x180002ae5  xor     rcx, rsp; StackCookie
0x180002ae8  call    __security_check_cookie
0x180002aed  add     rsp, 338h
0x180002af4  pop     r14
0x180002af6  pop     r13
0x180002af8  pop     r12
0x180002afa  pop     rdi
0x180002afb  pop     rbx
0x180002afc  pop     rbp
0x180002afd  retn
```
