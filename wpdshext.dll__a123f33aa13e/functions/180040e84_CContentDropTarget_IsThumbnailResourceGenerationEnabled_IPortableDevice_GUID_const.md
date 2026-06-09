# CContentDropTarget::_IsThumbnailResourceGenerationEnabled(IPortableDevice *,_GUID const &)

- ea: `0x180040e84`
- end: `0x18004121b`
- name: `?_IsThumbnailResourceGenerationEnabled@CContentDropTarget@@AEAAHPEAUIPortableDevice@@AEBU_GUID@@@Z`
- size: `919`
- prototype: `__int64 __fastcall(CContentDropTarget *__hidden this, struct IPortableDevice *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800118d4`

## callees

- `0x1800285c8`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003a650`
- `0x180040e84`
- `0x180078010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x1800410a6`
- `ole32!CLSIDFromString` at `0x180041149`
- `ole32!CLSIDFromString` at `0x1800410a6`
- `ole32!CLSIDFromString` at `0x180041149`
- `ole32!CoTaskMemFree` at `0x1800411d3`
- `ole32!CoTaskMemFree` at `0x1800411d3`
- `ole32!CoTaskMemAlloc` at `0x18004103a`
- `ole32!CoTaskMemAlloc` at `0x18004103a`
- `ole32!CoCreateInstance` at `0x180040f29`
- `ole32!CoCreateInstance` at `0x180040f29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CContentDropTarget::_IsThumbnailResourceGenerationEnabled(
        CContentDropTarget *this,
        struct IPortableDevice *a2,
        const struct _GUID *a3)
{
  unsigned int v6; // r15d
  HRESULT v7; // eax
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rax
  OLECHAR *v14; // rax
  OLECHAR *v15; // rbx
  __int64 v16; // rax
  unsigned int v17; // edi
  int v18; // eax
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  const OLECHAR *v22; // r12
  unsigned __int64 v23; // r14
  __int64 v24; // rax
  int v25; // eax
  SIZE_T cb; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  CLSID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[528]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  memset_0(v31, 0, 0x208u);
  cb = 0;
  pclsid = GUID_NULL;
  v6 = 0;
  v29 = 0;
  if ( a2 )
  {
    v7 = CoCreateInstance(&CLSID_PortableDeviceManager, 0, 1u, &GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40, &ppv);
    v8 = (unsigned int)v7;
    if ( v7 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD))(**((_QWORD **)this + 10) + 96LL))(
              *((_QWORD *)this + 10),
              v31,
              260,
              (unsigned int)v7);
      v8 = (unsigned int)v11;
      if ( v11 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, const wchar_t *, _QWORD, SIZE_T *, char *))(*(_QWORD *)ppv + 64LL))(
                ppv,
                v31,
                L"PortableDeviceNameSpaceThumbnailContentTypes",
                0,
                &cb,
                (char *)&cb + 4);
        if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147024774 )
        {
          if ( (_DWORD)cb )
          {
            v14 = (OLECHAR *)CoTaskMemAlloc((unsigned int)cb);
            v15 = v14;
            if ( v14 )
            {
              memset_0(v14, 0, (unsigned int)cb);
              if ( (*(int (__fastcall **)(LPVOID, _BYTE *, const wchar_t *, OLECHAR *, SIZE_T *, char *))(*(_QWORD *)ppv + 64LL))(
                     ppv,
                     v31,
                     L"PortableDeviceNameSpaceThumbnailContentTypes",
                     v15,
                     &cb,
                     (char *)&cb + 4) >= 0 )
              {
                if ( HIDWORD(cb) == 1 )
                {
                  if ( CLSIDFromString(v15, &pclsid) >= 0 )
                  {
                    v16 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a3->Data1;
                    if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a3->Data1 )
                      v16 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a3->Data4;
                    if ( !v16 )
                      v6 = 1;
                  }
                }
                else if ( HIDWORD(cb) == 7 )
                {
                  v17 = cb;
                  v18 = StringCbLengthW(v15, (unsigned int)cb, &v29);
                  v19 = (unsigned int)v18;
                  if ( v18 >= 0 )
                  {
                    v22 = v15;
                    while ( 1 )
                    {
                      v23 = v29;
                      if ( !v29 || !v17 )
                        break;
                      if ( CLSIDFromString(v22, &pclsid) >= 0 )
                      {
                        v24 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a3->Data1;
                        if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a3->Data1 )
                          v24 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a3->Data4;
                        if ( !v24 )
                        {
                          v6 = 1;
                          break;
                        }
                      }
                      v17 = -2 - v23 + cb;
                      LODWORD(cb) = v17;
                      v22 += (v23 >> 1) + 1;
                      v25 = StringCbLengthW(v22, v17, &v29);
                      v19 = (unsigned int)v25;
                      if ( v25 < 0 )
                      {
                        v20 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v21 = 239;
                          goto LABEL_42;
                        }
                        break;
                      }
                    }
                  }
                  else
                  {
                    v20 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v21 = 238;
LABEL_42:
                      WPP_SF_d(v20[2], v21, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v19);
                    }
                  }
                }
              }
              CoTaskMemFree(v15);
            }
          }
        }
        else
        {
          v13 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&WPD_CONTENT_TYPE_IMAGE.Data1;
          if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&WPD_CONTENT_TYPE_IMAGE.Data1 )
            v13 = *(_QWORD *)a3->Data4 - *(_QWORD *)WPD_CONTENT_TYPE_IMAGE.Data4;
          if ( !v13 )
            v6 = 1;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v10 = 237;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 236;
LABEL_6:
        WPP_SF_d(v9[2], v10, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids, v8);
      }
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v6;
}

```

## disassembly

```asm
0x180040e84  mov     [rsp-8+arg_8], rbx
0x180040e89  mov     [rsp-8+arg_10], rsi
0x180040e8e  push    rbp
0x180040e8f  push    rdi
0x180040e90  push    r12
0x180040e92  push    r14
0x180040e94  push    r15
0x180040e96  lea     rbp, [rsp-190h]
0x180040e9e  sub     rsp, 290h
0x180040ea5  mov     rax, cs:__security_cookie
0x180040eac  xor     rax, rsp
0x180040eaf  mov     [rbp+1B0h+var_30], rax
0x180040eb6  mov     rsi, r8
0x180040eb9  mov     rbx, rdx
0x180040ebc  mov     rdi, rcx
0x180040ebf  mov     [rsp+2B0h+var_268], 0
0x180040ec8  xor     edx, edx; Val
0x180040eca  mov     r8d, 208h; Size
0x180040ed0  lea     rcx, [rsp+2B0h+var_240]; void *
0x180040ed5  call    memset_0
0x180040eda  mov     dword ptr [rsp+2B0h+cb+4], 0
0x180040ee2  mov     dword ptr [rsp+2B0h+cb], 0
0x180040eea  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180040ef1  movdqu  xmmword ptr [rsp+2B0h+pclsid.Data1], xmm0
0x180040ef7  xor     r15d, r15d
0x180040efa  mov     [rsp+2B0h+var_260], r15
0x180040eff  test    rbx, rbx
0x180040f02  jz      loc_1800411DA
0x180040f08  lea     rax, [rsp+2B0h+var_268]
0x180040f0d  mov     [rsp+2B0h+ppv], rax; ppv
0x180040f12  lea     r9, _GUID_a1567595_4c2f_4574_a6fa_ecef917b9a40; riid
0x180040f19  lea     r14d, [r15+1]
0x180040f1d  mov     r8d, r14d; dwClsContext
0x180040f20  xor     edx, edx; pUnkOuter
0x180040f22  lea     rcx, CLSID_PortableDeviceManager; rclsid
0x180040f29  call    cs:__imp_CoCreateInstance
0x180040f2f  mov     r9d, eax
0x180040f32  test    eax, eax
0x180040f34  jns     short loc_180040F71
0x180040f36  lea     rax, WPP_GLOBAL_Control
0x180040f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f44  cmp     rcx, rax
0x180040f47  jz      loc_1800411DA
0x180040f4d  test    byte ptr [rcx+1Ch], 2
0x180040f51  jz      loc_1800411DA
0x180040f57  mov     edx, 0ECh
0x180040f5c  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x180040f63  mov     rcx, [rcx+10h]
0x180040f67  call    WPP_SF_d
0x180040f6c  jmp     loc_1800411DA
0x180040f71  mov     rcx, [rdi+50h]
0x180040f75  mov     rax, [rcx]
0x180040f78  mov     r8d, 104h
0x180040f7e  lea     rdx, [rsp+2B0h+var_240]
0x180040f83  mov     rax, [rax+60h]
0x180040f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040f8c  mov     r9d, eax
0x180040f8f  test    eax, eax
0x180040f91  jns     short loc_180040FBB
0x180040f93  lea     rax, WPP_GLOBAL_Control
0x180040f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040fa1  cmp     rcx, rax
0x180040fa4  jz      loc_1800411DA
0x180040faa  test    byte ptr [rcx+1Ch], 2
0x180040fae  jz      loc_1800411DA
0x180040fb4  mov     edx, 0EDh
0x180040fb9  jmp     short loc_180040F5C
0x180040fbb  mov     rcx, [rsp+2B0h+var_268]
0x180040fc0  mov     rax, [rcx]
0x180040fc3  lea     rdx, [rsp+2B0h+cb+4]
0x180040fc8  mov     [rsp+2B0h+var_288], rdx
0x180040fcd  lea     rdx, [rsp+2B0h+cb]
0x180040fd2  mov     [rsp+2B0h+ppv], rdx
0x180040fd7  xor     r9d, r9d
0x180040fda  lea     r8, aPortabledevice_3; "PortableDeviceNameSpaceThumbnailContent"...
0x180040fe1  lea     rdx, [rsp+2B0h+var_240]
0x180040fe6  mov     rax, [rax+40h]
0x180040fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040fef  mov     ecx, eax
0x180040ff1  mov     edx, 80000000h
0x180040ff6  add     eax, edx
0x180040ff8  test    edx, eax
0x180040ffa  jnz     short loc_18004102C
0x180040ffc  cmp     ecx, 8007007Ah
0x180041002  jz      short loc_18004102C
0x180041004  mov     rax, [rsi]
0x180041007  sub     rax, qword ptr cs:WPD_CONTENT_TYPE_IMAGE.Data1
0x18004100e  jnz     short loc_18004101B
0x180041010  mov     rax, [rsi+8]
0x180041014  sub     rax, qword ptr cs:WPD_CONTENT_TYPE_IMAGE.Data4
0x18004101b  test    rax, rax
0x18004101e  jnz     loc_1800411DA
0x180041024  mov     r15d, r14d
0x180041027  jmp     loc_1800411DA
0x18004102c  mov     eax, dword ptr [rsp+2B0h+cb]
0x180041030  test    eax, eax
0x180041032  jz      loc_1800411DA
0x180041038  mov     ecx, eax; cb
0x18004103a  call    cs:__imp_CoTaskMemAlloc
0x180041040  mov     rbx, rax
0x180041043  test    rax, rax
0x180041046  jz      loc_1800411DA
0x18004104c  mov     r8d, dword ptr [rsp+2B0h+cb]; Size
0x180041051  xor     edx, edx; Val
0x180041053  mov     rcx, rax; void *
0x180041056  call    memset_0
0x18004105b  mov     rcx, [rsp+2B0h+var_268]
0x180041060  mov     rax, [rcx]
0x180041063  lea     rdx, [rsp+2B0h+cb+4]
0x180041068  mov     [rsp+2B0h+var_288], rdx
0x18004106d  lea     rdx, [rsp+2B0h+cb]
0x180041072  mov     [rsp+2B0h+ppv], rdx
0x180041077  mov     r9, rbx
0x18004107a  lea     r8, aPortabledevice_3; "PortableDeviceNameSpaceThumbnailContent"...
0x180041081  lea     rdx, [rsp+2B0h+var_240]
0x180041086  mov     rax, [rax+40h]
0x18004108a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004108f  test    eax, eax
0x180041091  js      loc_1800411D0
0x180041097  cmp     dword ptr [rsp+2B0h+cb+4], r14d
0x18004109c  jnz     short loc_1800410D8
0x18004109e  lea     rdx, [rsp+2B0h+pclsid]; pclsid
0x1800410a3  mov     rcx, rbx; lpsz
0x1800410a6  call    cs:__imp_CLSIDFromString
0x1800410ac  test    eax, eax
0x1800410ae  js      loc_1800411D0
0x1800410b4  mov     rax, qword ptr [rsp+2B0h+pclsid.Data1]
0x1800410b9  sub     rax, [rsi]
0x1800410bc  jnz     short loc_1800410C7
0x1800410be  mov     rax, qword ptr [rsp+2B0h+pclsid.Data4]
0x1800410c3  sub     rax, [rsi+8]
0x1800410c7  test    rax, rax
0x1800410ca  jnz     loc_1800411D0
0x1800410d0  mov     r15d, r14d
0x1800410d3  jmp     loc_1800411D0
0x1800410d8  cmp     dword ptr [rsp+2B0h+cb+4], 7
0x1800410dd  jnz     loc_1800411D0
0x1800410e3  mov     edi, dword ptr [rsp+2B0h+cb]
0x1800410e7  mov     edx, edi; unsigned __int64
0x1800410e9  lea     r8, [rsp+2B0h+var_260]; unsigned __int64 *
0x1800410ee  mov     rcx, rbx; unsigned __int16 *
0x1800410f1  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800410f6  mov     r9d, eax
0x1800410f9  test    eax, eax
0x1800410fb  jns     short loc_180041128
0x1800410fd  lea     rax, WPP_GLOBAL_Control
0x180041104  mov     rcx, cs:WPP_GLOBAL_Control
0x18004110b  cmp     rcx, rax
0x18004110e  jz      loc_1800411D0
0x180041114  test    byte ptr [rcx+1Ch], 2
0x180041118  jz      loc_1800411D0
0x18004111e  mov     edx, 0EEh
0x180041123  jmp     loc_1800411C0
0x180041128  mov     r12, rbx
0x18004112b  mov     r14, [rsp+2B0h+var_260]
0x180041130  test    r14, r14
0x180041133  jz      loc_1800411D0
0x180041139  test    edi, edi
0x18004113b  jz      loc_1800411D0
0x180041141  lea     rdx, [rsp+2B0h+pclsid]; pclsid
0x180041146  mov     rcx, r12; lpsz
0x180041149  call    cs:__imp_CLSIDFromString
0x18004114f  test    eax, eax
0x180041151  js      short loc_18004116F
0x180041153  mov     rax, qword ptr [rsp+2B0h+pclsid.Data1]
0x180041158  sub     rax, [rsi]
0x18004115b  jnz     short loc_180041166
0x18004115d  mov     rax, qword ptr [rsp+2B0h+pclsid.Data4]
0x180041162  sub     rax, [rsi+8]
0x180041166  test    rax, rax
0x180041169  jz      loc_180041212
0x18004116f  mov     eax, 0FFFFFFFEh
0x180041174  sub     eax, r14d
0x180041177  mov     edi, dword ptr [rsp+2B0h+cb]
0x18004117b  add     edi, eax
0x18004117d  mov     dword ptr [rsp+2B0h+cb], edi
0x180041181  mov     edx, edi; unsigned __int64
0x180041183  shr     r14, 1
0x180041186  lea     r12, [r12+r14*2]
0x18004118a  add     r12, 2
0x18004118e  lea     r8, [rsp+2B0h+var_260]; unsigned __int64 *
0x180041193  mov     rcx, r12; unsigned __int16 *
0x180041196  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004119b  mov     r9d, eax
0x18004119e  test    eax, eax
0x1800411a0  jns     short loc_18004112B
0x1800411a2  lea     rax, WPP_GLOBAL_Control
0x1800411a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411b0  cmp     rcx, rax
0x1800411b3  jz      short loc_1800411D0
0x1800411b5  test    byte ptr [rcx+1Ch], 2
0x1800411b9  jz      short loc_1800411D0
0x1800411bb  mov     edx, 0EFh
0x1800411c0  lea     r8, WPP_b51af68ed3b130d123f9f1b846c4bbe3_Traceguids
0x1800411c7  mov     rcx, [rcx+10h]
0x1800411cb  call    WPP_SF_d
0x1800411d0  mov     rcx, rbx; pv
0x1800411d3  call    cs:__imp_CoTaskMemFree
0x1800411d9  nop
0x1800411da  lea     rcx, [rsp+2B0h+var_268]
0x1800411df  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800411e4  mov     eax, r15d
0x1800411e7  mov     rcx, [rbp+1B0h+var_30]
0x1800411ee  xor     rcx, rsp; StackCookie
0x1800411f1  call    __security_check_cookie
0x1800411f6  lea     r11, [rsp+2B0h+var_20]
0x1800411fe  mov     rbx, [r11+38h]
0x180041202  mov     rsi, [r11+40h]
0x180041206  mov     rsp, r11
0x180041209  pop     r15
0x18004120b  pop     r14
0x18004120d  pop     r12
0x18004120f  pop     rdi
0x180041210  pop     rbp
0x180041211  retn
0x180041212  mov     r15d, 1
0x180041218  jmp     short loc_1800411D0
```
