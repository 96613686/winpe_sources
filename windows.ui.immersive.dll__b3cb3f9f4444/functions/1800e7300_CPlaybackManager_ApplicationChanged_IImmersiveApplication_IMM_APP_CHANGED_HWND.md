# CPlaybackManager::ApplicationChanged(IImmersiveApplication *,IMM_APP_CHANGED,HWND__ *)

- ea: `0x1800e7300`
- end: `0x1800e75ed`
- name: `?ApplicationChanged@CPlaybackManager@@UEAAJPEAUIImmersiveApplication@@W4IMM_APP_CHANGED@@PEAUHWND__@@@Z`
- size: `749`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013f14`
- `0x1800e6c98`
- `0x1800e7300`
- `0x1800e7a70`
- `0x1800e85ec`
- `0x1800e90c4`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e75c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e75c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7391`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e74ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7391`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e74ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e748d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e75a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e748d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e75a8`

## pseudocode

```c
__int64 __fastcall CPlaybackManager::ApplicationChanged(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 (__fastcall ***a2)(__int64, GUID *, __int64 *),
        unsigned int a3)
{
  unsigned __int64 v4; // rax
  CPlaybackManager *p_LockSemaphore; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 (__fastcall **v7)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v8)(__int64, GUID *, __int64 *); // rbx
  unsigned int v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  unsigned __int64 i; // rax
  HANDLE *v12; // r14
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  __int64 (__fastcall **v14)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v15)(__int64, GUID *, __int64 *); // rbx
  int v17; // [rsp+38h] [rbp-19h] BYREF
  __int64 v18; // [rsp+40h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-9h] BYREF
  int v20; // [rsp+50h] [rbp-1h] BYREF
  int v21; // [rsp+54h] [rbp+3h] BYREF
  int v22; // [rsp+58h] [rbp+7h] BYREF
  int v23[2]; // [rsp+60h] [rbp+Fh] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp+17h] BYREF
  _QWORD v25[5]; // [rsp+70h] [rbp+1Fh] BYREF
  unsigned int v26; // [rsp+C8h] [rbp+77h] BYREF

  v26 = a3;
  v17 = 1;
  v20 = 0;
  v22 = 0;
  v4 = 0;
  v23[0] = 0;
  v21 = 0;
  pv = 0;
  v24 = -1;
  while ( v4 < 4 )
  {
    if ( dword_1801101E0[v4] == a3 )
    {
      p_LockSemaphore = (CPlaybackManager *)&a1[-4].LockSemaphore;
      if ( LOBYTE(a1[4].LockCount) )
      {
        v6 = a1 + 3;
        EnterCriticalSection(a1 + 3);
        v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), LPVOID *))(*a2)[4])(
                a2,
                &pv);
        if ( v17 >= 0 )
        {
          v7 = *a2;
          v18 = 0;
          v8 = *v7;
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
          v17 = v8((__int64)a2, &GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3, &v18);
          if ( v17 >= 0 )
          {
            v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v18 + 24LL))(v18, &v24);
            if ( v17 >= 0 )
            {
              v17 = CPlaybackManager::ComputeAggregateApplicationState(p_LockSemaphore, v24, &v20, &v22, v23, &v21);
              if ( v17 >= 0 )
              {
                if ( v26 == 6 && v20 || v26 == 14 && v21 || v26 == 5 && v21 )
                {
                  v17 = -2147467260;
                }
                else
                {
                  v9 = CPlaybackManager::IamAppChanged_2_PbmInteractivityChanged(
                         p_LockSemaphore,
                         v26,
                         (unsigned int)v22);
                  v17 = CPlaybackManager::ReportAppInteractivityChange(p_LockSemaphore, pv, v24, v9);
                }
              }
            }
          }
          CoTaskMemFree(pv);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
        }
        if ( v6 )
        {
          v10 = v6;
LABEL_36:
          LeaveCriticalSection(v10);
        }
        return (unsigned int)v17;
      }
      break;
    }
    ++v4;
  }
  for ( i = 0; i < 2; ++i )
  {
    if ( dword_1801101F0[i] == a3 )
    {
      v12 = &a1[-4].LockSemaphore;
      if ( LOBYTE(a1[4].LockCount) )
      {
        v13 = a1 + 3;
        EnterCriticalSection(a1 + 3);
        v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), LPVOID *))(*a2)[4])(
                a2,
                &pv);
        if ( v17 >= 0 )
        {
          v14 = *a2;
          v18 = 0;
          v15 = *v14;
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
          v17 = v15((__int64)a2, &GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3, &v18);
          if ( v17 >= 0 )
          {
            *(_QWORD *)v23 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 24LL))(v18, v23);
            if ( v17 >= 0 )
            {
              if ( v26 == 11 || v26 == 16 )
              {
                v25[1] = v12;
                v25[0] = &v17;
                v25[2] = &pv;
                v25[3] = v23;
                v25[4] = &v26;
                lambda_2e05f4b5582b515c2c6be785142243e4_::operator()(v25);
              }
              CoTaskMemFree(pv);
            }
          }
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
        }
        if ( v13 )
        {
          v10 = v13;
          goto LABEL_36;
        }
      }
      return (unsigned int)v17;
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800e7300  mov     rax, rsp
0x1800e7303  mov     [rax+8], rbx
0x1800e7307  mov     [rax+10h], rsi
0x1800e730b  mov     [rax+18h], r8d
0x1800e730f  push    rbp
0x1800e7310  push    rdi
0x1800e7311  push    r14
0x1800e7313  lea     rbp, [rax-5Fh]
0x1800e7317  sub     rsp, 90h
0x1800e731e  mov     rsi, rdx
0x1800e7321  mov     [rbp+57h+var_70], 1
0x1800e7328  lea     rdx, __ImageBase
0x1800e732f  mov     [rbp+57h+var_58], 0
0x1800e7336  mov     [rbp+57h+var_50], 0
0x1800e733d  xor     eax, eax
0x1800e733f  mov     [rbp+57h+var_48], 0
0x1800e7346  mov     [rbp+57h+var_54], 0
0x1800e734d  mov     [rbp+57h+pv], 0
0x1800e7355  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800e735d  cmp     rax, 4
0x1800e7361  jnb     loc_1800E74B3
0x1800e7367  cmp     ds:rva dword_1801101E0[rdx+rax*4], r8d
0x1800e736f  jz      short loc_1800E7376
0x1800e7371  inc     rax
0x1800e7374  jmp     short loc_1800E735D
0x1800e7376  lea     rdi, [rcx-88h]
0x1800e737d  cmp     byte ptr [rdi+130h], 0
0x1800e7384  jz      loc_1800E74B3
0x1800e738a  lea     r14, [rcx+78h]
0x1800e738e  mov     rcx, r14; lpCriticalSection
0x1800e7391  call    cs:__imp_EnterCriticalSection
0x1800e7398  nop     dword ptr [rax+rax+00h]
0x1800e739d  mov     rax, [rsi]
0x1800e73a0  lea     rdx, [rbp+57h+pv]
0x1800e73a4  mov     rcx, rsi
0x1800e73a7  mov     rax, [rax+20h]
0x1800e73ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e73b0  mov     [rbp+57h+var_70], eax
0x1800e73b3  test    eax, eax
0x1800e73b5  js      loc_1800E74A2
0x1800e73bb  mov     rax, [rsi]
0x1800e73be  lea     rcx, [rbp+57h+var_68]
0x1800e73c2  mov     [rbp+57h+var_68], 0
0x1800e73ca  mov     rbx, [rax]
0x1800e73cd  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e73d2  lea     r8, [rbp+57h+var_68]
0x1800e73d6  mov     rcx, rsi
0x1800e73d9  lea     rdx, _GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3
0x1800e73e0  mov     rax, rbx
0x1800e73e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e73e8  mov     [rbp+57h+var_70], eax
0x1800e73eb  test    eax, eax
0x1800e73ed  js      loc_1800E7489
0x1800e73f3  mov     rcx, [rbp+57h+var_68]
0x1800e73f7  lea     rdx, [rbp+57h+var_40]
0x1800e73fb  mov     rax, [rcx]
0x1800e73fe  mov     rax, [rax+18h]
0x1800e7402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7407  mov     [rbp+57h+var_70], eax
0x1800e740a  test    eax, eax
0x1800e740c  js      short loc_1800E7489
0x1800e740e  mov     rdx, [rbp+57h+var_40]; unsigned __int64
0x1800e7412  lea     rax, [rbp+57h+var_54]
0x1800e7416  mov     [rsp+0A0h+var_78], rax; int *
0x1800e741b  lea     r9, [rbp+57h+var_50]; int *
0x1800e741f  lea     rax, [rbp+57h+var_48]
0x1800e7423  mov     rcx, rdi; this
0x1800e7426  lea     r8, [rbp+57h+var_58]; int *
0x1800e742a  mov     [rsp+0A0h+var_80], rax; int *
0x1800e742f  call    ?ComputeAggregateApplicationState@CPlaybackManager@@AEAAJ_KPEAH111@Z; CPlaybackManager::ComputeAggregateApplicationState(unsigned __int64,int *,int *,int *,int *)
0x1800e7434  mov     [rbp+57h+var_70], eax
0x1800e7437  test    eax, eax
0x1800e7439  js      short loc_1800E7489
0x1800e743b  mov     edx, [rbp+57h+arg_10]
0x1800e743e  cmp     edx, 6
0x1800e7441  jnz     short loc_1800E7449
0x1800e7443  cmp     [rbp+57h+var_58], 0
0x1800e7447  jnz     short loc_1800E745E
0x1800e7449  mov     eax, [rbp+57h+var_54]
0x1800e744c  cmp     edx, 0Eh
0x1800e744f  jnz     short loc_1800E7455
0x1800e7451  test    eax, eax
0x1800e7453  jnz     short loc_1800E745E
0x1800e7455  cmp     edx, 5
0x1800e7458  jnz     short loc_1800E7467
0x1800e745a  test    eax, eax
0x1800e745c  jz      short loc_1800E7467
0x1800e745e  mov     [rbp+57h+var_70], 80004004h
0x1800e7465  jmp     short loc_1800E7489
0x1800e7467  mov     r8d, [rbp+57h+var_50]
0x1800e746b  mov     rcx, rdi
0x1800e746e  call    ?IamAppChanged_2_PbmInteractivityChanged@CPlaybackManager@@AEAA?AW4__MIDL___MIDL_itf_playbackmanagerrpc_0000_0000_0001@@W4IMM_APP_CHANGED@@H@Z; CPlaybackManager::IamAppChanged_2_PbmInteractivityChanged(IMM_APP_CHANGED,int)
0x1800e7473  mov     r8, [rbp+57h+var_40]
0x1800e7477  mov     r9d, eax
0x1800e747a  mov     rdx, [rbp+57h+pv]
0x1800e747e  mov     rcx, rdi
0x1800e7481  call    ?ReportAppInteractivityChange@CPlaybackManager@@AEAAJPEBG_KW4__MIDL___MIDL_itf_playbackmanagerrpc_0000_0000_0001@@@Z; CPlaybackManager::ReportAppInteractivityChange(ushort const *,unsigned __int64,__MIDL___MIDL_itf_playbackmanagerrpc_0000_0000_0001)
0x1800e7486  mov     [rbp+57h+var_70], eax
0x1800e7489  mov     rcx, [rbp+57h+pv]; pv
0x1800e748d  call    cs:__imp_CoTaskMemFree
0x1800e7494  nop     dword ptr [rax+rax+00h]
0x1800e7499  lea     rcx, [rbp+57h+var_68]
0x1800e749d  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e74a2  test    r14, r14
0x1800e74a5  jz      loc_1800E75D1
0x1800e74ab  mov     rcx, r14
0x1800e74ae  jmp     loc_1800E75C5
0x1800e74b3  xor     eax, eax
0x1800e74b5  cmp     rax, 2
0x1800e74b9  jnb     loc_1800E75D1
0x1800e74bf  cmp     ds:rva dword_1801101F0[rdx+rax*4], r8d
0x1800e74c7  jz      short loc_1800E74CE
0x1800e74c9  inc     rax
0x1800e74cc  jmp     short loc_1800E74B5
0x1800e74ce  lea     r14, [rcx-88h]
0x1800e74d5  cmp     byte ptr [r14+130h], 0
0x1800e74dd  jz      loc_1800E75D1
0x1800e74e3  lea     rdi, [rcx+78h]
0x1800e74e7  mov     rcx, rdi; lpCriticalSection
0x1800e74ea  call    cs:__imp_EnterCriticalSection
0x1800e74f1  nop     dword ptr [rax+rax+00h]
0x1800e74f6  mov     rax, [rsi]
0x1800e74f9  lea     rdx, [rbp+57h+pv]
0x1800e74fd  mov     rcx, rsi
0x1800e7500  mov     rax, [rax+20h]
0x1800e7504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7509  mov     [rbp+57h+var_70], eax
0x1800e750c  test    eax, eax
0x1800e750e  js      loc_1800E75BD
0x1800e7514  mov     rax, [rsi]
0x1800e7517  lea     rcx, [rbp+57h+var_68]
0x1800e751b  mov     [rbp+57h+var_68], 0
0x1800e7523  mov     rbx, [rax]
0x1800e7526  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e752b  lea     r8, [rbp+57h+var_68]
0x1800e752f  mov     rcx, rsi
0x1800e7532  lea     rdx, _GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3
0x1800e7539  mov     rax, rbx
0x1800e753c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7541  mov     [rbp+57h+var_70], eax
0x1800e7544  test    eax, eax
0x1800e7546  js      short loc_1800E75B4
0x1800e7548  mov     rcx, [rbp+57h+var_68]
0x1800e754c  lea     rdx, [rbp+57h+var_48]
0x1800e7550  mov     qword ptr [rbp+57h+var_48], 0
0x1800e7558  mov     rax, [rcx]
0x1800e755b  mov     rax, [rax+18h]
0x1800e755f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e7564  mov     [rbp+57h+var_70], eax
0x1800e7567  test    eax, eax
0x1800e7569  js      short loc_1800E75B4
0x1800e756b  cmp     [rbp+57h+arg_10], 0Bh
0x1800e756f  jz      short loc_1800E7577
0x1800e7571  cmp     [rbp+57h+arg_10], 10h
0x1800e7575  jnz     short loc_1800E75A4
0x1800e7577  lea     rax, [rbp+57h+var_70]
0x1800e757b  mov     [rbp+57h+var_30], r14
0x1800e757f  mov     [rbp+57h+var_38], rax
0x1800e7583  lea     rcx, [rbp+57h+var_38]
0x1800e7587  lea     rax, [rbp+57h+pv]
0x1800e758b  mov     [rbp+57h+var_28], rax
0x1800e758f  lea     rax, [rbp+57h+var_48]
0x1800e7593  mov     [rbp+57h+var_20], rax
0x1800e7597  lea     rax, [rbp+57h+arg_10]
0x1800e759b  mov     [rbp+57h+var_18], rax
0x1800e759f  call    _lambda_2e05f4b5582b515c2c6be785142243e4___operator__
0x1800e75a4  mov     rcx, [rbp+57h+pv]; pv
0x1800e75a8  call    cs:__imp_CoTaskMemFree
0x1800e75af  nop     dword ptr [rax+rax+00h]
0x1800e75b4  lea     rcx, [rbp+57h+var_68]
0x1800e75b8  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800e75bd  test    rdi, rdi
0x1800e75c0  jz      short loc_1800E75D1
0x1800e75c2  mov     rcx, rdi; lpCriticalSection
0x1800e75c5  call    cs:__imp_LeaveCriticalSection
0x1800e75cc  nop     dword ptr [rax+rax+00h]
0x1800e75d1  mov     eax, [rbp+57h+var_70]
0x1800e75d4  lea     r11, [rsp+0A0h+var_10]
0x1800e75dc  mov     rbx, [r11+20h]
0x1800e75e0  mov     rsi, [r11+28h]
0x1800e75e4  mov     rsp, r11
0x1800e75e7  pop     r14
0x1800e75e9  pop     rdi
0x1800e75ea  pop     rbp
0x1800e75eb  retn
```
