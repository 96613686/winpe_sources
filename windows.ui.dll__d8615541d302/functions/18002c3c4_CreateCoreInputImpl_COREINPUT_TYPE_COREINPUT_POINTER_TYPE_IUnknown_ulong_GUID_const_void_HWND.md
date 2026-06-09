# CreateCoreInputImpl(_COREINPUT_TYPE,_COREINPUT_POINTER_TYPE,IUnknown *,ulong,_GUID const &,void * *,HWND__ *)

- ea: `0x18002c3c4`
- end: `0x18002c6e2`
- name: `?CreateCoreInputImpl@@YAJW4_COREINPUT_TYPE@@W4_COREINPUT_POINTER_TYPE@@PEAUIUnknown@@KAEBU_GUID@@PEAPEAXPEAUHWND__@@@Z`
- size: `798`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002c340`
- `0x18002c380`
- `0x18006faf0`
- `0x18006fb30`
- `0x180071b80`

## callees

- `0x1800038e0`
- `0x18002c3c4`
- `0x18002c6e8`
- `0x18002ca94`
- `0x1800582ac`
- `0x180071bbc`
- `0x180071c10`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c4f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c511`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c57b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c5be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c66e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c4f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c511`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c57b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c5be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c66e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c6bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 CreateCoreInputImpl(int a1, int a2, __int64 a3, int a4, __int64 a5, ...)
{
  __int64 *v7; // r15
  int v8; // r14d
  __int64 v10; // rcx
  PVOID *v11; // rax
  DWORD v12; // eax
  __int64 v13; // r8
  DWORD CurrentThreadId; // eax
  __int64 v15; // rbx
  DWORD v16; // eax
  DWORD v17; // eax
  __int64 v18; // rbx
  DWORD v19; // eax
  DWORD v20; // eax
  __int64 v21; // r8
  _QWORD v22[3]; // [rsp+30h] [rbp-18h] BYREF
  int v23; // [rsp+80h] [rbp+38h] BYREF
  int v24; // [rsp+88h] [rbp+40h] BYREF
  __int64 v25; // [rsp+90h] [rbp+48h] BYREF
  int v26; // [rsp+98h] [rbp+50h] BYREF
  __int64 *v27; // [rsp+A8h] [rbp+60h] BYREF
  va_list va; // [rsp+A8h] [rbp+60h]
  va_list va1; // [rsp+B0h] [rbp+68h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v27 = va_arg(va1, __int64 *);
  v26 = a4;
  v25 = a3;
  v24 = a2;
  v23 = a1;
  v7 = v27;
  *v27 = 0;
  if ( a1 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids,
        CurrentThreadId);
    }
    v22[0] = 0;
    LODWORD(v27) = 15;
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v22);
    v8 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>,Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>,enum _COREINPUT_TYPE &,enum _COREINPUT_POINTER_TYPE &,unsigned long &,IUnknown * &,HWND__ * &>(
           (unsigned int)v22,
           (unsigned int)&v23,
           (unsigned int)va,
           (unsigned int)&v26,
           (__int64)&v25,
           (__int64)va1);
    if ( v8 >= 0 )
    {
      v8 = (**(__int64 (__fastcall ***)(_QWORD, __int64, __int64 *))v22[0])(v22[0], a5, v7);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v15 = *v7;
        v16 = GetCurrentThreadId();
        WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids, v16, v15);
      }
    }
    v10 = v22[0];
    if ( v22[0] )
    {
      v22[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  else
  {
    v8 = -2147024809;
    if ( a1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = GetCurrentThreadId();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v21, v20, a1);
      }
    }
    else
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v17 = GetCurrentThreadId();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids, v17);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( !a2 || (a2 & 0xFFFFFFF8) != 0 )
      {
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x40) != 0 && *((_BYTE *)v11 + 25) >= 2u )
        {
          v12 = GetCurrentThreadId();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v13, v12, a2);
        }
      }
      else
      {
        v27 = 0;
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((__int64 **)va);
        v8 = Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>,Windows::UI::Core::CCoreInput<&unsigned short const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>,enum _COREINPUT_TYPE &,enum _COREINPUT_POINTER_TYPE &,unsigned long &,IUnknown * &,HWND__ * &>(
               (unsigned int)va,
               (unsigned int)&v23,
               (unsigned int)&v24,
               (unsigned int)&v26,
               (__int64)&v25,
               (__int64)va1);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))*v27)(v27, a5, v7);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            v18 = *v7;
            v19 = GetCurrentThreadId();
            WPP_SF_Dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              &WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids,
              v19,
              v18);
          }
        }
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((__int64 **)va);
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c3c4  mov     rax, rsp
0x18002c3c7  mov     [rax+20h], r9d
0x18002c3cb  mov     [rax+18h], r8
0x18002c3cf  mov     [rax+10h], edx
0x18002c3d2  mov     [rax+8], ecx
0x18002c3d5  push    rbp
0x18002c3d6  push    rbx
0x18002c3d7  push    rsi
0x18002c3d8  push    rdi
0x18002c3d9  push    r14
0x18002c3db  push    r15
0x18002c3dd  mov     rbp, rsp
0x18002c3e0  sub     rsp, 48h
0x18002c3e4  mov     esi, edx
0x18002c3e6  mov     edi, ecx
0x18002c3e8  mov     r15, [rbp+arg_28]
0x18002c3ec  mov     qword ptr [r15], 0
0x18002c3f3  cmp     ecx, 1
0x18002c3f6  jz      short loc_18002C42D
0x18002c3f8  mov     r14d, 80070057h
0x18002c3fe  test    ecx, ecx
0x18002c400  jz      loc_18002C4B7
0x18002c406  lea     rbx, WPP_GLOBAL_Control
0x18002c40d  mov     rax, cs:WPP_GLOBAL_Control
0x18002c414  cmp     rax, rbx
0x18002c417  jnz     loc_18002C6A7
0x18002c41d  mov     eax, r14d
0x18002c420  add     rsp, 48h
0x18002c424  pop     r15
0x18002c426  pop     r14
0x18002c428  pop     rdi
0x18002c429  pop     rsi
0x18002c42a  pop     rbx
0x18002c42b  pop     rbp
0x18002c42c  retn
0x18002c42d  lea     rbx, WPP_GLOBAL_Control
0x18002c434  mov     rax, cs:WPP_GLOBAL_Control
0x18002c43b  cmp     rax, rbx
0x18002c43e  jz      short loc_18002C44A
0x18002c440  test    byte ptr [rax+1Ch], 40h
0x18002c444  jnz     loc_18002C507
0x18002c44a  mov     [rbp+var_18], 0
0x18002c452  mov     dword ptr [rbp+arg_28], 0Fh
0x18002c459  lea     rcx, [rbp+var_18]
0x18002c45d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002c462  lea     rax, [rbp+arg_30]
0x18002c466  mov     [rsp+48h+var_20], rax
0x18002c46b  lea     rax, [rbp+arg_10]
0x18002c46f  mov     [rsp+48h+var_28], rax
0x18002c474  lea     r9, [rbp+arg_18]
0x18002c478  lea     r8, [rbp+arg_28]
0x18002c47c  lea     rdx, [rbp+arg_0]
0x18002c480  lea     rcx, [rbp+var_18]
0x18002c484  call    ??$MakeAndInitialize@V?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@V1234@AEAW4_COREINPUT_TYPE@@AEAW4_COREINPUT_POINTER_TYPE@@AEAKAEAPEAUIUnknown@@AEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAV?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreComponentInputSource@@3QBGB@Core@UI@Windows@@AEAW4_COREINPUT_TYPE@@AEAW4_COREINPUT_POINTER_TYPE@@AEAKAEAPEAUIUnknown@@AEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>,Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource>,_COREINPUT_TYPE &,_COREINPUT_POINTER_TYPE &,ulong &,IUnknown * &,HWND__ * &>(Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreComponentInputSource> * *,_COREINPUT_TYPE &,_COREINPUT_POINTER_TYPE &,ulong &,IUnknown * &,HWND__ * &)
0x18002c489  mov     r14d, eax
0x18002c48c  test    eax, eax
0x18002c48e  jns     loc_18002C53B
0x18002c494  mov     rcx, [rbp+var_18]
0x18002c498  test    rcx, rcx
0x18002c49b  jz      short loc_18002C4B2
0x18002c49d  mov     [rbp+var_18], 0
0x18002c4a5  mov     rax, [rcx]
0x18002c4a8  mov     rax, [rax+10h]
0x18002c4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4b1  nop
0x18002c4b2  jmp     loc_18002C41D
0x18002c4b7  lea     rbx, WPP_GLOBAL_Control
0x18002c4be  mov     rax, cs:WPP_GLOBAL_Control
0x18002c4c5  cmp     rax, rbx
0x18002c4c8  jnz     loc_18002C5AA
0x18002c4ce  test    esi, esi
0x18002c4d0  jnz     loc_18002C5EF
0x18002c4d6  cmp     rax, rbx
0x18002c4d9  jz      loc_18002C41D
0x18002c4df  test    byte ptr [rax+1Ch], 40h
0x18002c4e3  jz      loc_18002C41D
0x18002c4e9  cmp     byte ptr [rax+19h], 2
0x18002c4ed  jb      loc_18002C41D
0x18002c4f3  call    cs:__imp_GetCurrentThreadId
0x18002c4f9  mov     edx, 0Eh
0x18002c4fe  mov     dword ptr [rsp+48h+var_28], esi
0x18002c502  jmp     loc_18002C6CA
0x18002c507  cmp     byte ptr [rax+19h], 4
0x18002c50b  jb      loc_18002C44A
0x18002c511  call    cs:__imp_GetCurrentThreadId
0x18002c517  mov     edx, 0Ah
0x18002c51c  mov     r9d, eax
0x18002c51f  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18002c526  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c52d  mov     rcx, [rcx+10h]
0x18002c531  call    WPP_SF_d
0x18002c536  jmp     loc_18002C44A
0x18002c53b  mov     rcx, [rbp+var_18]
0x18002c53f  mov     rax, [rcx]
0x18002c542  mov     r8, r15
0x18002c545  mov     rdx, [rbp+arg_20]
0x18002c549  mov     rax, [rax]
0x18002c54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c551  mov     r14d, eax
0x18002c554  mov     rax, cs:WPP_GLOBAL_Control
0x18002c55b  cmp     rax, rbx
0x18002c55e  jz      loc_18002C494
0x18002c564  test    byte ptr [rax+1Ch], 40h
0x18002c568  jz      loc_18002C494
0x18002c56e  cmp     byte ptr [rax+19h], 4
0x18002c572  jb      loc_18002C494
0x18002c578  mov     rbx, [r15]
0x18002c57b  call    cs:__imp_GetCurrentThreadId
0x18002c581  mov     edx, 0Bh
0x18002c586  mov     [rsp+48h+var_28], rbx
0x18002c58b  mov     r9d, eax
0x18002c58e  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18002c595  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c59c  mov     rcx, [rcx+10h]
0x18002c5a0  call    WPP_SF_Dq
0x18002c5a5  jmp     loc_18002C494
0x18002c5aa  test    byte ptr [rax+1Ch], 40h
0x18002c5ae  jz      loc_18002C4CE
0x18002c5b4  cmp     byte ptr [rax+19h], 4
0x18002c5b8  jb      loc_18002C4CE
0x18002c5be  call    cs:__imp_GetCurrentThreadId
0x18002c5c4  mov     edx, 0Ch
0x18002c5c9  mov     r9d, eax
0x18002c5cc  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18002c5d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5da  mov     rcx, [rcx+10h]
0x18002c5de  call    WPP_SF_d
0x18002c5e3  mov     rax, cs:WPP_GLOBAL_Control
0x18002c5ea  jmp     loc_18002C4CE
0x18002c5ef  test    esi, 0FFFFFFF8h
0x18002c5f5  jnz     loc_18002C4D6
0x18002c5fb  mov     [rbp+arg_28], 0
0x18002c603  lea     rcx, [rbp+arg_28]
0x18002c607  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002c60c  lea     rax, [rbp+arg_30]
0x18002c610  mov     [rsp+48h+var_20], rax
0x18002c615  lea     rax, [rbp+arg_10]
0x18002c619  mov     [rsp+48h+var_28], rax
0x18002c61e  lea     r9, [rbp+arg_18]
0x18002c622  lea     r8, [rbp+arg_8]
0x18002c626  lea     rdx, [rbp+arg_0]
0x18002c62a  lea     rcx, [rbp+arg_28]
0x18002c62e  call    ??$MakeAndInitialize@V?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@V1234@AEAW4_COREINPUT_TYPE@@AEAW4_COREINPUT_POINTER_TYPE@@AEAKAEAPEAUIUnknown@@AEAPEAUHWND__@@@Details@WRL@Microsoft@@YAJPEAPEAV?$CCoreInput@$1?RuntimeClass_Windows_UI_Core_CoreIndependentInputSource@@3QBGB@Core@UI@Windows@@AEAW4_COREINPUT_TYPE@@AEAW4_COREINPUT_POINTER_TYPE@@AEAKAEAPEAUIUnknown@@AEAPEAUHWND__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>,Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource>,_COREINPUT_TYPE &,_COREINPUT_POINTER_TYPE &,ulong &,IUnknown * &,HWND__ * &>(Windows::UI::Core::CCoreInput<&ushort const near * const RuntimeClass_Windows_UI_Core_CoreIndependentInputSource> * *,_COREINPUT_TYPE &,_COREINPUT_POINTER_TYPE &,ulong &,IUnknown * &,HWND__ * &)
0x18002c633  mov     r14d, eax
0x18002c636  test    eax, eax
0x18002c638  js      short loc_18002C699
0x18002c63a  mov     rcx, [rbp+arg_28]
0x18002c63e  mov     rax, [rcx]
0x18002c641  mov     r8, r15
0x18002c644  mov     rdx, [rbp+arg_20]
0x18002c648  mov     rax, [rax]
0x18002c64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c650  mov     r14d, eax
0x18002c653  mov     rax, cs:WPP_GLOBAL_Control
0x18002c65a  cmp     rax, rbx
0x18002c65d  jz      short loc_18002C699
0x18002c65f  test    byte ptr [rax+1Ch], 40h
0x18002c663  jz      short loc_18002C699
0x18002c665  cmp     byte ptr [rax+19h], 4
0x18002c669  jb      short loc_18002C699
0x18002c66b  mov     rbx, [r15]
0x18002c66e  call    cs:__imp_GetCurrentThreadId
0x18002c674  mov     edx, 0Dh
0x18002c679  mov     [rsp+48h+var_28], rbx
0x18002c67e  mov     r9d, eax
0x18002c681  lea     r8, WPP_3b510a2a222231b0f6327a10e76445fa_Traceguids
0x18002c688  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c68f  mov     rcx, [rcx+10h]
0x18002c693  call    WPP_SF_Dq
0x18002c698  nop
0x18002c699  lea     rcx, [rbp+arg_28]
0x18002c69d  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002c6a2  jmp     loc_18002C41D
0x18002c6a7  test    byte ptr [rax+1Ch], 40h
0x18002c6ab  jz      loc_18002C41D
0x18002c6b1  cmp     byte ptr [rax+19h], 2
0x18002c6b5  jb      loc_18002C41D
0x18002c6bb  call    cs:__imp_GetCurrentThreadId
0x18002c6c1  mov     edx, 0Fh
0x18002c6c6  mov     dword ptr [rsp+48h+var_28], edi
0x18002c6ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6d1  mov     r9d, eax
0x18002c6d4  mov     rcx, [rcx+10h]
0x18002c6d8  call    WPP_SF_Dd
0x18002c6dd  jmp     loc_18002C41D
```
