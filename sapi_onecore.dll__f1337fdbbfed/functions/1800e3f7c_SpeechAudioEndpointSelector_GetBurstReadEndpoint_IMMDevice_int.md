# SpeechAudioEndpointSelector::GetBurstReadEndpoint(IMMDevice * *,int)

- ea: `0x1800e3f7c`
- end: `0x1800e41ec`
- name: `?GetBurstReadEndpoint@SpeechAudioEndpointSelector@@QEAAJPEAPEAUIMMDevice@@H@Z`
- size: `624`
- prototype: `__int64 __fastcall(SpeechAudioEndpointSelector *__hidden this, struct IMMDevice **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f144`

## callees

- `0x180021944`
- `0x180026508`
- `0x1800e3f7c`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e41a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e41b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e41a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e41b4`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e4047`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e4154`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e4047`
- `MMDevAPI!__imp_mmdDevGetInterfaceIdFromMMDevice` at `0x1800e4154`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e4069`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e4176`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e4069`
- `MMDevAPI!__imp_mmdDevGetRelatedInterfaceId` at `0x1800e4176`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SpeechAudioEndpointSelector::GetBurstReadEndpoint(
        SpeechAudioEndpointSelector *this,
        struct IMMDevice **a2,
        int a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, _QWORD, struct IMMDevice **); // rbx
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  struct IMMDevice *v12; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64, __int128 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  unsigned int i; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, struct IMMDevice **); // rbx
  struct IMMDevice *v20; // rax
  int v22; // [rsp+20h] [rbp-40h]
  __int128 v23; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-20h] BYREF
  LPVOID v25; // [rsp+48h] [rbp-18h] BYREF
  __int128 v26; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int v28; // [rsp+98h] [rbp+38h] BYREF
  struct IMMDevice *v29; // [rsp+A8h] [rbp+48h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v29 = 0;
    v25 = 0;
    pv = 0;
    v7 = *((_QWORD *)this + 2);
    v8 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v7 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v9 = v8(v7, 1, 0, &v29);
    v6 = v9;
    if ( v9 >= 0 )
    {
      if ( v29 )
      {
        if ( !(unsigned int)mmdDevGetInterfaceIdFromMMDevice(v29, &pv) )
        {
          v23 = *(_OWORD *)&DEVINTERFACE_AUDIO_KEYWORDDETECTOR;
          if ( !(unsigned int)mmdDevGetRelatedInterfaceId(pv, &v23, &v25) )
          {
            v12 = v29;
            v29 = 0;
            *a2 = v12;
          }
        }
        if ( *a2 || a3 )
        {
LABEL_26:
          v6 = 0;
        }
        else
        {
          *(_QWORD *)&v23 = 0;
          v28 = 0;
          v13 = *((_QWORD *)this + 2);
          v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v13 + 24LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
          v15 = v14(v13, 1, 1, &v23);
          v6 = v15;
          if ( v15 >= 0 )
          {
            v15 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v23 + 24LL))(v23, &v28);
            v6 = v15;
            if ( v15 >= 0 )
            {
              for ( i = 0; ; ++i )
              {
                if ( i >= v28 )
                  goto LABEL_25;
                v18 = v23;
                v19 = *(__int64 (__fastcall **)(__int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v23 + 32LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
                v15 = v19(v18, i, &v29);
                v6 = v15;
                if ( v15 < 0 )
                  break;
                if ( !(unsigned int)mmdDevGetInterfaceIdFromMMDevice(v29, &pv) )
                {
                  v26 = *(_OWORD *)&DEVINTERFACE_AUDIO_KEYWORDDETECTOR;
                  if ( !(unsigned int)mmdDevGetRelatedInterfaceId(pv, &v26, &v25) )
                  {
                    v20 = v29;
                    v29 = 0;
                    *a2 = v20;
LABEL_25:
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
                    goto LABEL_26;
                  }
                }
              }
              v16 = 171;
            }
            else
            {
              v16 = 167;
            }
          }
          else
          {
            v16 = 166;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\internal\\speechaudioendpointselector.cpp",
            (const char *)(unsigned int)v15,
            v22);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
        }
        goto LABEL_27;
      }
      v6 = -2147023728;
      v10 = 2147943568LL;
      v11 = 152;
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 151;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\internal\\speechaudioendpointselector.cpp",
      (const char *)v10,
      v22);
LABEL_27:
    CoTaskMemFree(pv);
    pv = 0;
    CoTaskMemFree(v25);
    v25 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    return v6;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F,
    (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\internal\\speechaudioendpointselector.cpp",
    (const char *)0x80004003LL,
    v22);
  return v6;
}

```

## disassembly

```asm
0x1800e3f7c  mov     [rsp-28h+arg_0], rbx
0x1800e3f81  push    rbp
0x1800e3f82  push    rsi
0x1800e3f83  push    rdi
0x1800e3f84  push    r14
0x1800e3f86  push    r15
0x1800e3f88  mov     rbp, rsp
0x1800e3f8b  sub     rsp, 60h
0x1800e3f8f  mov     esi, r8d
0x1800e3f92  mov     r14, rdx
0x1800e3f95  mov     r15, rcx
0x1800e3f98  test    rdx, rdx
0x1800e3f9b  jnz     short loc_1800E3FBF
0x1800e3f9d  mov     rcx, [rbp+28h]; this
0x1800e3fa1  mov     ebx, 80004003h
0x1800e3fa6  mov     r9d, ebx; char *
0x1800e3fa9  lea     r8, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800e3fb0  mov     edx, 8Fh; void *
0x1800e3fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3fba  jmp     loc_1800E41CB
0x1800e3fbf  mov     qword ptr [rdx], 0
0x1800e3fc6  mov     [rbp+arg_18], 0
0x1800e3fce  mov     [rbp+var_18], 0
0x1800e3fd6  mov     [rbp+pv], 0
0x1800e3fde  mov     rdi, [rcx+10h]
0x1800e3fe2  mov     rax, [rdi]
0x1800e3fe5  mov     rbx, [rax+20h]
0x1800e3fe9  lea     rcx, [rbp+arg_18]
0x1800e3fed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e3ff2  lea     r9, [rbp+arg_18]
0x1800e3ff6  xor     r8d, r8d
0x1800e3ff9  lea     edx, [r8+1]
0x1800e3ffd  mov     rcx, rdi
0x1800e4000  mov     rax, rbx
0x1800e4003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4008  mov     ebx, eax
0x1800e400a  test    eax, eax
0x1800e400c  jns     short loc_1800E4018
0x1800e400e  mov     r9d, eax
0x1800e4011  mov     edx, 97h
0x1800e4016  jmp     short loc_1800E402E
0x1800e4018  mov     rcx, [rbp+arg_18]
0x1800e401c  test    rcx, rcx
0x1800e401f  jnz     short loc_1800E4043
0x1800e4021  mov     ebx, 80070490h
0x1800e4026  mov     r9d, ebx; char *
0x1800e4029  mov     edx, 98h; void *
0x1800e402e  lea     r8, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800e4035  mov     rcx, [rbp+28h]; this
0x1800e4039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e403e  jmp     loc_1800E419E
0x1800e4043  lea     rdx, [rbp+pv]
0x1800e4047  call    cs:__imp_mmdDevGetInterfaceIdFromMMDevice
0x1800e404d  test    eax, eax
0x1800e404f  jnz     short loc_1800E4082
0x1800e4051  movups  xmm0, cs:DEVINTERFACE_AUDIO_KEYWORDDETECTOR
0x1800e4058  movdqu  [rbp+var_30], xmm0
0x1800e405d  lea     r8, [rbp+var_18]
0x1800e4061  lea     rdx, [rbp+var_30]
0x1800e4065  mov     rcx, [rbp+pv]
0x1800e4069  call    cs:__imp_mmdDevGetRelatedInterfaceId
0x1800e406f  test    eax, eax
0x1800e4071  jnz     short loc_1800E4082
0x1800e4073  mov     rax, [rbp+arg_18]
0x1800e4077  mov     [rbp+arg_18], 0
0x1800e407f  mov     [r14], rax
0x1800e4082  cmp     qword ptr [r14], 0
0x1800e4086  jnz     loc_1800E419C
0x1800e408c  test    esi, esi
0x1800e408e  jnz     loc_1800E419C
0x1800e4094  mov     qword ptr [rbp+var_30], 0
0x1800e409c  mov     [rbp+arg_8], esi
0x1800e409f  mov     rdi, [r15+10h]
0x1800e40a3  mov     rax, [rdi]
0x1800e40a6  mov     rbx, [rax+18h]
0x1800e40aa  lea     rcx, [rbp+var_30]
0x1800e40ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e40b3  lea     r9, [rbp+var_30]
0x1800e40b7  lea     edx, [rsi+1]
0x1800e40ba  mov     r8d, edx
0x1800e40bd  mov     rcx, rdi
0x1800e40c0  mov     rax, rbx
0x1800e40c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e40c8  mov     ebx, eax
0x1800e40ca  test    eax, eax
0x1800e40cc  jns     short loc_1800E40F5
0x1800e40ce  mov     edx, 0A6h; void *
0x1800e40d3  mov     rcx, [rbp+28h]; this
0x1800e40d7  mov     r9d, eax; char *
0x1800e40da  lea     r8, aOnecoreuapEndu_35; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800e40e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e40e6  nop
0x1800e40e7  lea     rcx, [rbp+var_30]
0x1800e40eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e40f0  jmp     loc_1800E419E
0x1800e40f5  mov     rcx, qword ptr [rbp+var_30]
0x1800e40f9  mov     rax, [rcx]
0x1800e40fc  lea     rdx, [rbp+arg_8]
0x1800e4100  mov     rax, [rax+18h]
0x1800e4104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4109  mov     ebx, eax
0x1800e410b  test    eax, eax
0x1800e410d  jns     short loc_1800E4116
0x1800e410f  mov     edx, 0A7h
0x1800e4114  jmp     short loc_1800E40D3
0x1800e4116  xor     esi, esi
0x1800e4118  cmp     esi, [rbp+arg_8]
0x1800e411b  jnb     short loc_1800E4193
0x1800e411d  mov     rdi, qword ptr [rbp+var_30]
0x1800e4121  mov     rax, [rdi]
0x1800e4124  mov     rbx, [rax+20h]
0x1800e4128  lea     rcx, [rbp+arg_18]
0x1800e412c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e4131  lea     r8, [rbp+arg_18]
0x1800e4135  mov     edx, esi
0x1800e4137  mov     rcx, rdi
0x1800e413a  mov     rax, rbx
0x1800e413d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4142  mov     ebx, eax
0x1800e4144  test    eax, eax
0x1800e4146  js      loc_1800E41E1
0x1800e414c  lea     rdx, [rbp+pv]
0x1800e4150  mov     rcx, [rbp+arg_18]
0x1800e4154  call    cs:__imp_mmdDevGetInterfaceIdFromMMDevice
0x1800e415a  test    eax, eax
0x1800e415c  jnz     short loc_1800E4180
0x1800e415e  movups  xmm0, cs:DEVINTERFACE_AUDIO_KEYWORDDETECTOR
0x1800e4165  movdqu  [rbp+var_10], xmm0
0x1800e416a  lea     r8, [rbp+var_18]
0x1800e416e  lea     rdx, [rbp+var_10]
0x1800e4172  mov     rcx, [rbp+pv]
0x1800e4176  call    cs:__imp_mmdDevGetRelatedInterfaceId
0x1800e417c  test    eax, eax
0x1800e417e  jz      short loc_1800E4184
0x1800e4180  inc     esi
0x1800e4182  jmp     short loc_1800E4118
0x1800e4184  mov     rax, [rbp+arg_18]
0x1800e4188  mov     [rbp+arg_18], 0
0x1800e4190  mov     [r14], rax
0x1800e4193  lea     rcx, [rbp+var_30]
0x1800e4197  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e419c  xor     ebx, ebx
0x1800e419e  mov     rcx, [rbp+pv]; pv
0x1800e41a2  call    cs:__imp_CoTaskMemFree
0x1800e41a8  mov     [rbp+pv], 0
0x1800e41b0  mov     rcx, [rbp+var_18]; pv
0x1800e41b4  call    cs:__imp_CoTaskMemFree
0x1800e41ba  mov     [rbp+var_18], 0
0x1800e41c2  lea     rcx, [rbp+arg_18]
0x1800e41c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e41cb  mov     eax, ebx
0x1800e41cd  mov     rbx, [rsp+60h+arg_0]
0x1800e41d5  add     rsp, 60h
0x1800e41d9  pop     r15
0x1800e41db  pop     r14
0x1800e41dd  pop     rdi
0x1800e41de  pop     rsi
0x1800e41df  pop     rbp
0x1800e41e0  retn
0x1800e41e1  mov     edx, 0ABh
0x1800e41e6  jmp     loc_1800E40D3
```
