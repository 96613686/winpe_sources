# SpeechAudioEndpointSelector::GetBurstReadDeviceInterface(ushort * *,int,ulong *)

- ea: `0x1800e3cec`
- end: `0x1800e3f73`
- name: `?GetBurstReadDeviceInterface@SpeechAudioEndpointSelector@@QEAAJPEAPEAGHPEAK@Z`
- size: `647`
- prototype: `__int64 __fastcall(SpeechAudioEndpointSelector *__hidden this, unsigned __int16 **, int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bf9e0`

## callees

- `0x180021944`
- `0x180026508`
- `0x1800e3cec`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3f36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3f24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e3f36`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e3dbd`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e3eca`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e3dbd`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e3eca`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e3ddf`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e3eec`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e3ddf`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e3eec`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SpeechAudioEndpointSelector::GetBurstReadDeviceInterface(
        SpeechAudioEndpointSelector *this,
        unsigned __int16 **a2,
        int a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, _QWORD, __int64 *); // rbx
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned __int16 *v14; // rax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64, __int64, __int128 *); // rbx
  int v17; // eax
  __int64 v18; // rdx
  unsigned int i; // esi
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64 *); // rbx
  unsigned __int16 *v22; // rax
  int v24; // [rsp+20h] [rbp-50h]
  __int128 v25; // [rsp+30h] [rbp-40h] BYREF
  LPVOID v26; // [rsp+40h] [rbp-30h] BYREF
  __int64 v27; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-20h] BYREF
  __int128 v29; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  unsigned int v31; // [rsp+A8h] [rbp+38h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v27 = 0;
    v26 = 0;
    pv[0] = 0;
    v9 = *((_QWORD *)this + 2);
    v10 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v9 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v11 = v10(v9, 1, 0, &v27);
    v8 = v11;
    if ( v11 >= 0 )
    {
      if ( v27 )
      {
        if ( !(unsigned int)mmdDevGetInterfaceIdFromMMDevice(v27, pv) )
        {
          v25 = *(_OWORD *)&DEVINTERFACE_AUDIO_KEYWORDDETECTOR;
          if ( !(unsigned int)mmdDevGetRelatedInterfaceId(pv[0], &v25, &v26) )
          {
            v14 = (unsigned __int16 *)v26;
            v26 = 0;
            *a2 = v14;
          }
        }
        if ( *a2 || a3 )
        {
LABEL_26:
          if ( a4 )
            *a4 = *((_DWORD *)this + 6);
          v8 = 0;
        }
        else
        {
          *(_QWORD *)&v25 = 0;
          v31 = 0;
          v15 = *((_QWORD *)this + 2);
          v16 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v15 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
          v17 = v16(v15, 1, 1, &v25);
          v8 = v17;
          if ( v17 >= 0 )
          {
            v17 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v25 + 24LL))(v25, &v31);
            v8 = v17;
            if ( v17 >= 0 )
            {
              for ( i = 0; ; ++i )
              {
                if ( i >= v31 )
                  goto LABEL_25;
                v20 = v25;
                v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 32LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
                v17 = v21(v20, i, &v27);
                v8 = v17;
                if ( v17 < 0 )
                  break;
                if ( !(unsigned int)mmdDevGetInterfaceIdFromMMDevice(v27, pv) )
                {
                  v29 = *(_OWORD *)&DEVINTERFACE_AUDIO_KEYWORDDETECTOR;
                  if ( !(unsigned int)mmdDevGetRelatedInterfaceId(pv[0], &v29, &v26) )
                  {
                    v22 = (unsigned __int16 *)v26;
                    v26 = 0;
                    *a2 = v22;
LABEL_25:
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
                    goto LABEL_26;
                  }
                }
              }
              v18 = 122;
            }
            else
            {
              v18 = 118;
            }
          }
          else
          {
            v18 = 117;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\internal\\speechaudioendpointselector.cpp",
            (const char *)(unsigned int)v17,
            v24);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        }
        goto LABEL_29;
      }
      v8 = -2147023728;
      v12 = 2147943568LL;
      v13 = 103;
    }
    else
    {
      v12 = (unsigned int)v11;
      v13 = 102;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\internal\\speechaudioendpointselector.cpp",
      (const char *)v12,
      v24);
LABEL_29:
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
    CoTaskMemFree(v26);
    v26 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    return v8;
  }
  v8 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5E,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\internal\\speechaudioendpointselector.cpp",
    (const char *)0x80004003LL,
    v24);
  return v8;
}

```

## disassembly

```asm
0x1800e3cec  mov     [rsp-28h+arg_0], rbx
0x1800e3cf1  mov     [rsp-28h+arg_10], rsi
0x1800e3cf6  push    rbp
0x1800e3cf7  push    rdi
0x1800e3cf8  push    r13
0x1800e3cfa  push    r14
0x1800e3cfc  push    r15
0x1800e3cfe  mov     rbp, rsp
0x1800e3d01  sub     rsp, 70h
0x1800e3d05  mov     r15, r9
0x1800e3d08  mov     esi, r8d
0x1800e3d0b  mov     r14, rdx
0x1800e3d0e  mov     r13, rcx
0x1800e3d11  test    rdx, rdx
0x1800e3d14  jnz     short loc_1800E3D37
0x1800e3d16  mov     rcx, [rbp+28h]; this
0x1800e3d1a  mov     ebx, 80004003h
0x1800e3d1f  mov     r9d, ebx; char *
0x1800e3d22  lea     r8, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800e3d29  lea     edx, [r14+5Eh]; void *
0x1800e3d2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3d32  jmp     loc_1800E3F4D
0x1800e3d37  mov     qword ptr [rdx], 0
0x1800e3d3e  mov     [rbp+var_28], 0
0x1800e3d46  mov     [rbp+var_30], 0
0x1800e3d4e  mov     [rbp+pv], 0
0x1800e3d56  mov     rdi, [rcx+10h]
0x1800e3d5a  mov     rax, [rdi]
0x1800e3d5d  mov     rbx, [rax+20h]
0x1800e3d61  lea     rcx, [rbp+var_28]
0x1800e3d65  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3d6a  lea     r9, [rbp+var_28]
0x1800e3d6e  xor     r8d, r8d
0x1800e3d71  lea     edx, [r8+1]
0x1800e3d75  mov     rcx, rdi
0x1800e3d78  mov     rax, rbx
0x1800e3d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3d80  mov     ebx, eax
0x1800e3d82  test    eax, eax
0x1800e3d84  jns     short loc_1800E3D90
0x1800e3d86  mov     r9d, eax
0x1800e3d89  mov     edx, 66h ; 'f'
0x1800e3d8e  jmp     short loc_1800E3DA4
0x1800e3d90  mov     rcx, [rbp+var_28]
0x1800e3d94  test    rcx, rcx
0x1800e3d97  jnz     short loc_1800E3DB9
0x1800e3d99  mov     ebx, 80070490h
0x1800e3d9e  mov     r9d, ebx; char *
0x1800e3da1  lea     edx, [rcx+67h]; void *
0x1800e3da4  lea     r8, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800e3dab  mov     rcx, [rbp+28h]; this
0x1800e3daf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3db4  jmp     loc_1800E3F20
0x1800e3db9  lea     rdx, [rbp+pv]
0x1800e3dbd  call    cs:__imp_mmdDevGetInterfaceIdFromMMDevice
0x1800e3dc3  test    eax, eax
0x1800e3dc5  jnz     short loc_1800E3DF8
0x1800e3dc7  movups  xmm0, cs:DEVINTERFACE_AUDIO_KEYWORDDETECTOR
0x1800e3dce  movdqu  [rbp+var_40], xmm0
0x1800e3dd3  lea     r8, [rbp+var_30]
0x1800e3dd7  lea     rdx, [rbp+var_40]
0x1800e3ddb  mov     rcx, [rbp+pv]
0x1800e3ddf  call    cs:__imp_mmdDevGetRelatedInterfaceId
0x1800e3de5  test    eax, eax
0x1800e3de7  jnz     short loc_1800E3DF8
0x1800e3de9  mov     rax, [rbp+var_30]
0x1800e3ded  mov     [rbp+var_30], 0
0x1800e3df5  mov     [r14], rax
0x1800e3df8  cmp     qword ptr [r14], 0
0x1800e3dfc  jnz     loc_1800E3F12
0x1800e3e02  test    esi, esi
0x1800e3e04  jnz     loc_1800E3F12
0x1800e3e0a  mov     qword ptr [rbp+var_40], 0
0x1800e3e12  mov     [rbp+arg_8], esi
0x1800e3e15  mov     rdi, [r13+10h]
0x1800e3e19  mov     rax, [rdi]
0x1800e3e1c  mov     rbx, [rax+18h]
0x1800e3e20  lea     rcx, [rbp+var_40]
0x1800e3e24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3e29  lea     r9, [rbp+var_40]
0x1800e3e2d  lea     eax, [rsi+1]
0x1800e3e30  mov     r8d, eax
0x1800e3e33  mov     edx, eax
0x1800e3e35  mov     rcx, rdi
0x1800e3e38  mov     rax, rbx
0x1800e3e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3e40  mov     ebx, eax
0x1800e3e42  test    eax, eax
0x1800e3e44  jns     short loc_1800E3E6B
0x1800e3e46  lea     edx, [rsi+75h]; void *
0x1800e3e49  mov     rcx, [rbp+28h]; this
0x1800e3e4d  mov     r9d, eax; char *
0x1800e3e50  lea     r8, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800e3e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3e5c  nop
0x1800e3e5d  lea     rcx, [rbp+var_40]
0x1800e3e61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3e66  jmp     loc_1800E3F20
0x1800e3e6b  mov     rcx, qword ptr [rbp+var_40]
0x1800e3e6f  mov     rax, [rcx]
0x1800e3e72  lea     rdx, [rbp+arg_8]
0x1800e3e76  mov     rax, [rax+18h]
0x1800e3e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3e7f  mov     ebx, eax
0x1800e3e81  test    eax, eax
0x1800e3e83  jns     short loc_1800E3E8C
0x1800e3e85  mov     edx, 76h ; 'v'
0x1800e3e8a  jmp     short loc_1800E3E49
0x1800e3e8c  xor     esi, esi
0x1800e3e8e  cmp     esi, [rbp+arg_8]
0x1800e3e91  jnb     short loc_1800E3F09
0x1800e3e93  mov     rdi, qword ptr [rbp+var_40]
0x1800e3e97  mov     rax, [rdi]
0x1800e3e9a  mov     rbx, [rax+20h]
0x1800e3e9e  lea     rcx, [rbp+var_28]
0x1800e3ea2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3ea7  lea     r8, [rbp+var_28]
0x1800e3eab  mov     edx, esi
0x1800e3ead  mov     rcx, rdi
0x1800e3eb0  mov     rax, rbx
0x1800e3eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3eb8  mov     ebx, eax
0x1800e3eba  test    eax, eax
0x1800e3ebc  js      loc_1800E3F68
0x1800e3ec2  lea     rdx, [rbp+pv]
0x1800e3ec6  mov     rcx, [rbp+var_28]
0x1800e3eca  call    cs:__imp_mmdDevGetInterfaceIdFromMMDevice
0x1800e3ed0  test    eax, eax
0x1800e3ed2  jnz     short loc_1800E3EF6
0x1800e3ed4  movups  xmm0, cs:DEVINTERFACE_AUDIO_KEYWORDDETECTOR
0x1800e3edb  movdqu  [rbp+var_10], xmm0
0x1800e3ee0  lea     r8, [rbp+var_30]
0x1800e3ee4  lea     rdx, [rbp+var_10]
0x1800e3ee8  mov     rcx, [rbp+pv]
0x1800e3eec  call    cs:__imp_mmdDevGetRelatedInterfaceId
0x1800e3ef2  test    eax, eax
0x1800e3ef4  jz      short loc_1800E3EFA
0x1800e3ef6  inc     esi
0x1800e3ef8  jmp     short loc_1800E3E8E
0x1800e3efa  mov     rax, [rbp+var_30]
0x1800e3efe  mov     [rbp+var_30], 0
0x1800e3f06  mov     [r14], rax
0x1800e3f09  lea     rcx, [rbp+var_40]
0x1800e3f0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3f12  test    r15, r15
0x1800e3f15  jz      short loc_1800E3F1E
0x1800e3f17  mov     eax, [r13+18h]
0x1800e3f1b  mov     [r15], eax
0x1800e3f1e  xor     ebx, ebx
0x1800e3f20  mov     rcx, [rbp+pv]; pv
0x1800e3f24  call    cs:__imp_CoTaskMemFree
0x1800e3f2a  mov     [rbp+pv], 0
0x1800e3f32  mov     rcx, [rbp+var_30]; pv
0x1800e3f36  call    cs:__imp_CoTaskMemFree
0x1800e3f3c  mov     [rbp+var_30], 0
0x1800e3f44  lea     rcx, [rbp+var_28]
0x1800e3f48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3f4d  mov     eax, ebx
0x1800e3f4f  lea     r11, [rsp+70h+var_s0]
0x1800e3f54  mov     rbx, [r11+30h]
0x1800e3f58  mov     rsi, [r11+40h]
0x1800e3f5c  mov     rsp, r11
0x1800e3f5f  pop     r15
0x1800e3f61  pop     r14
0x1800e3f63  pop     r13
0x1800e3f65  pop     rdi
0x1800e3f66  pop     rbp
0x1800e3f67  retn
0x1800e3f68  mov     edx, 7Ah ; 'z'
0x1800e3f6d  jmp     loc_1800E3E49
```
