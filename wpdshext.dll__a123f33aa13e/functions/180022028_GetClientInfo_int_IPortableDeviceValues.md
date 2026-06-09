# GetClientInfo(int,IPortableDeviceValues * *)

- ea: `0x180022028`
- end: `0x180022259`
- name: `?GetClientInfo@@YAJHPEAPEAUIPortableDeviceValues@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(int, struct IPortableDeviceValues **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180021de0`
- `0x18006ac50`

## callees

- `0x180022028`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x180078010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180022078`
- `ole32!CoCreateInstance` at `0x180022078`
- `ole32!StringFromGUID2` at `0x1800221c1`
- `ole32!StringFromGUID2` at `0x1800221c1`

## pseudocode

```c
__int64 __fastcall GetClientInfo(int a1, LPVOID *a2)
{
  HRESULT v4; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-29h] BYREF

  *a2 = 0;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_PortableDeviceValues, 0, 1u, &GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, const wchar_t *))(*(_QWORD *)ppv + 56LL))(
           ppv,
           &WPD_CLIENT_NAME,
           L"Portable Devices Namespace");
    if ( !v4 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)ppv + 72LL))(
             ppv,
             &WPD_CLIENT_MAJOR_VERSION,
             10);
      if ( !v4 )
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, _QWORD))(*(_QWORD *)ppv + 72LL))(
               ppv,
               &WPD_CLIENT_MINOR_VERSION,
               0);
        if ( !v4 )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)ppv + 72LL))(
                 ppv,
                 &WPD_CLIENT_REVISION,
                 29595);
          if ( !v4 )
          {
            v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64 *, __int64))(*(_QWORD *)ppv + 232LL))(
                   ppv,
                   &WPD_CLIENT_WMDRM_APPLICATION_PRIVATE_KEY,
                   qword_18007EF30,
                   4096);
            if ( !v4 )
            {
              v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64 *, __int64))(*(_QWORD *)ppv + 232LL))(
                     ppv,
                     &WPD_CLIENT_WMDRM_APPLICATION_CERTIFICATE,
                     qword_180083500,
                     100);
              if ( !v4 )
              {
                v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, __int64))(*(_QWORD *)ppv + 72LL))(
                       ppv,
                       &WPD_CLIENT_SECURITY_QUALITY_OF_SERVICE,
                       0x20000);
                if ( !v4 )
                {
                  if ( !a1 )
                  {
LABEL_12:
                    *a2 = ppv;
                    return (unsigned int)v4;
                  }
                  memset_0(sz, 0, 0x4Eu);
                  StringFromGUID2(&CLSID_WPD_NAMESPACE_EXTENSION, sz, v4 + 39);
                  v4 = (*(__int64 (__fastcall **)(LPVOID, const PROPERTYKEY *, OLECHAR *))(*(_QWORD *)ppv + 56LL))(
                         ppv,
                         &WPD_CLIENT_EVENT_COOKIE,
                         sz);
                }
              }
            }
          }
        }
      }
    }
    if ( v4 >= 0 )
      goto LABEL_12;
    if ( ppv )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180022028  push    rbp
0x18002202a  push    rbx
0x18002202b  push    rsi
0x18002202c  push    rdi
0x18002202d  lea     rbp, [rsp-3Fh]
0x180022032  sub     rsp, 0A8h
0x180022039  mov     rax, cs:__security_cookie
0x180022040  xor     rax, rsp
0x180022043  mov     [rbp+57h+var_30], rax
0x180022047  mov     rdi, rdx
0x18002204a  mov     qword ptr [rdx], 0
0x180022051  xor     edx, edx; pUnkOuter
0x180022053  mov     [rbp+57h+var_90], 0
0x18002205b  mov     esi, ecx
0x18002205d  lea     rax, [rbp+57h+var_90]
0x180022061  lea     r9, _GUID_6848f6f2_3155_4f86_b6f5_263eeeab3143; riid
0x180022068  mov     [rsp+0C0h+ppv], rax; ppv
0x18002206d  lea     rcx, CLSID_PortableDeviceValues; rclsid
0x180022074  lea     r8d, [rdx+1]; dwClsContext
0x180022078  call    cs:__imp_CoCreateInstance
0x18002207e  mov     ebx, eax
0x180022080  test    eax, eax
0x180022082  js      loc_18002220E
0x180022088  mov     rcx, [rbp+57h+var_90]
0x18002208c  lea     r8, aPortableDevice; "Portable Devices Namespace"
0x180022093  lea     rdx, WPD_CLIENT_NAME
0x18002209a  mov     rax, [rcx]
0x18002209d  mov     rax, [rax+38h]
0x1800220a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220a6  mov     ebx, eax
0x1800220a8  test    eax, eax
0x1800220aa  jnz     loc_1800221E4
0x1800220b0  mov     rcx, [rbp+57h+var_90]
0x1800220b4  lea     r8d, [rbx+0Ah]
0x1800220b8  lea     rdx, WPD_CLIENT_MAJOR_VERSION
0x1800220bf  mov     rax, [rcx]
0x1800220c2  mov     rax, [rax+48h]
0x1800220c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220cb  mov     ebx, eax
0x1800220cd  test    eax, eax
0x1800220cf  jnz     loc_1800221E4
0x1800220d5  mov     rcx, [rbp+57h+var_90]
0x1800220d9  lea     rdx, WPD_CLIENT_MINOR_VERSION
0x1800220e0  xor     r8d, r8d
0x1800220e3  mov     rax, [rcx]
0x1800220e6  mov     rax, [rax+48h]
0x1800220ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ef  mov     ebx, eax
0x1800220f1  test    eax, eax
0x1800220f3  jnz     loc_1800221E4
0x1800220f9  mov     rcx, [rbp+57h+var_90]
0x1800220fd  lea     rdx, WPD_CLIENT_REVISION
0x180022104  mov     r8d, 739Bh
0x18002210a  mov     rax, [rcx]
0x18002210d  mov     rax, [rax+48h]
0x180022111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022116  mov     ebx, eax
0x180022118  test    eax, eax
0x18002211a  jnz     loc_1800221E4
0x180022120  mov     rcx, [rbp+57h+var_90]
0x180022124  lea     r8, qword_18007EF30
0x18002212b  mov     r9d, 1000h
0x180022131  lea     rdx, WPD_CLIENT_WMDRM_APPLICATION_PRIVATE_KEY
0x180022138  mov     rax, [rcx]
0x18002213b  mov     rax, [rax+0E8h]
0x180022142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022147  mov     ebx, eax
0x180022149  test    eax, eax
0x18002214b  jnz     loc_1800221E4
0x180022151  mov     rcx, [rbp+57h+var_90]
0x180022155  lea     r9d, [rbx+64h]
0x180022159  lea     r8, qword_180083500
0x180022160  lea     rdx, WPD_CLIENT_WMDRM_APPLICATION_CERTIFICATE
0x180022167  mov     rax, [rcx]
0x18002216a  mov     rax, [rax+0E8h]
0x180022171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022176  mov     ebx, eax
0x180022178  test    eax, eax
0x18002217a  jnz     short loc_1800221E4
0x18002217c  mov     rcx, [rbp+57h+var_90]
0x180022180  lea     rdx, WPD_CLIENT_SECURITY_QUALITY_OF_SERVICE
0x180022187  mov     r8d, 20000h
0x18002218d  mov     rax, [rcx]
0x180022190  mov     rax, [rax+48h]
0x180022194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022199  mov     ebx, eax
0x18002219b  test    eax, eax
0x18002219d  jnz     short loc_1800221E4
0x18002219f  test    esi, esi
0x1800221a1  jz      short loc_1800221E8
0x1800221a3  xor     edx, edx; Val
0x1800221a5  lea     r8d, [rax+4Eh]; Size
0x1800221a9  lea     rcx, [rbp+57h+sz]; void *
0x1800221ad  call    memset_0
0x1800221b2  lea     r8d, [rbx+27h]; cchMax
0x1800221b6  lea     rdx, [rbp+57h+sz]; lpsz
0x1800221ba  lea     rcx, CLSID_WPD_NAMESPACE_EXTENSION; rguid
0x1800221c1  call    cs:__imp_StringFromGUID2
0x1800221c7  mov     rcx, [rbp+57h+var_90]
0x1800221cb  lea     r8, [rbp+57h+sz]
0x1800221cf  lea     rdx, WPD_CLIENT_EVENT_COOKIE
0x1800221d6  mov     rax, [rcx]
0x1800221d9  mov     rax, [rax+38h]
0x1800221dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221e2  mov     ebx, eax
0x1800221e4  test    ebx, ebx
0x1800221e6  js      short loc_1800221F1
0x1800221e8  mov     rax, [rbp+57h+var_90]
0x1800221ec  mov     [rdi], rax
0x1800221ef  jmp     short loc_18002223F
0x1800221f1  mov     rcx, [rbp+57h+var_90]
0x1800221f5  test    rcx, rcx
0x1800221f8  jz      short loc_18002220E
0x1800221fa  mov     rax, [rcx]
0x1800221fd  mov     rax, [rax+10h]
0x180022201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022206  mov     [rbp+57h+var_90], 0
0x18002220e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022215  lea     rax, WPP_GLOBAL_Control
0x18002221c  cmp     rcx, rax
0x18002221f  jz      short loc_18002223F
0x180022221  test    byte ptr [rcx+1Ch], 2
0x180022225  jz      short loc_18002223F
0x180022227  mov     rcx, [rcx+10h]
0x18002222b  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x180022232  mov     edx, 0Ah
0x180022237  mov     r9d, ebx
0x18002223a  call    WPP_SF_d
0x18002223f  mov     eax, ebx
0x180022241  mov     rcx, [rbp+57h+var_30]
0x180022245  xor     rcx, rsp; StackCookie
0x180022248  call    __security_check_cookie
0x18002224d  add     rsp, 0A8h
0x180022254  pop     rdi
0x180022255  pop     rsi
0x180022256  pop     rbx
0x180022257  pop     rbp
0x180022258  retn
```
