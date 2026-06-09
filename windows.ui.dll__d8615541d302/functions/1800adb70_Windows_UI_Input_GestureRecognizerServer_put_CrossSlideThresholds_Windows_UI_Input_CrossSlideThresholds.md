# Windows::UI::Input::GestureRecognizerServer::put_CrossSlideThresholds(Windows::UI::Input::CrossSlideThresholds)

- ea: `0x1800adb70`
- end: `0x1800add8f`
- name: `?put_CrossSlideThresholds@GestureRecognizerServer@Input@UI@Windows@@UEAAJUCrossSlideThresholds@234@@Z`
- size: `543`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18003b648`
- `0x18003b670`
- `0x1800aba74`
- `0x1800adb70`
- `0x1800c73c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800adbac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800adbac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800adc16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800add5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800adc16`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800add5e`
- `NInput!SetCrossSlideParametersInteractionContext` at `0x1800adc51`
- `NInput!SetCrossSlideParametersInteractionContext` at `0x1800add50`
- `NInput!SetCrossSlideParametersInteractionContext` at `0x1800adc51`
- `NInput!SetCrossSlideParametersInteractionContext` at `0x1800add50`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800adcf7`
- `NInput!SetInteractionConfigurationInteractionContext` at `0x1800adcf7`
- `NInput!GetInteractionConfigurationInteractionContext` at `0x1800adc80`
- `NInput!GetInteractionConfigurationInteractionContext` at `0x1800adc80`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::GestureRecognizerServer::put_CrossSlideThresholds(__int64 a1, float *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  int MustCacheSettings; // eax
  __int64 v6; // rcx
  __int128 v7; // xmm0
  unsigned __int64 InteractionConfigurationInteractionContext; // rdi
  int v10; // edx
  __int64 v11; // rcx
  int v12; // edx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rcx
  int v17; // edx
  __int128 v18; // xmm0
  _DWORD v19[4]; // [rsp+28h] [rbp-29h] BYREF
  __int128 v20; // [rsp+38h] [rbp-19h] BYREF
  __int128 v21; // [rsp+48h] [rbp-9h] BYREF
  _DWORD v22[8]; // [rsp+58h] [rbp+7h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 584);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 584));
  *(_DWORD *)(a1 + 576) &= ~0x100u;
  v22[0] = -1;
  v22[2] = -1;
  v22[4] = -1;
  v22[6] = -1;
  v19[0] = 4;
  v22[1] = 0;
  v22[3] = 0;
  v22[5] = 0;
  v22[7] = 0;
  MustCacheSettings = Windows::UI::Input::GestureRecognizerServer::MustCacheSettings((Windows::UI::Input::GestureRecognizerServer *)a1);
  v7 = *(_OWORD *)a2;
  if ( MustCacheSettings )
  {
    *(_DWORD *)(a1 + 576) |= 0x100u;
    *(_OWORD *)(a1 + 520) = v7;
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    v20 = *(_OWORD *)a2;
    LODWORD(InteractionConfigurationInteractionContext) = Windows::UI::Input::GestureRecognizerServer::ConvertCrossSlideValuesToIC(
                                                            v6,
                                                            &v20,
                                                            v22,
                                                            v19);
    if ( (InteractionConfigurationInteractionContext & 0x80000000) == 0LL )
    {
      LODWORD(InteractionConfigurationInteractionContext) = SetCrossSlideParametersInteractionContext(
                                                              *(_QWORD *)(a1 + 296),
                                                              v19[0],
                                                              v22);
      TouchWinRT::OnErrorOriginateError((TouchWinRT *)(unsigned int)InteractionConfigurationInteractionContext, v10);
      if ( (InteractionConfigurationInteractionContext & 0x80000000) == 0LL )
      {
        v11 = *(_QWORD *)(a1 + 296);
        *(_QWORD *)&v20 = 6;
        InteractionConfigurationInteractionContext = (unsigned int)GetInteractionConfigurationInteractionContext(
                                                                     v11,
                                                                     1,
                                                                     &v20);
        TouchWinRT::OnErrorOriginateError((TouchWinRT *)InteractionConfigurationInteractionContext, v12);
        if ( (InteractionConfigurationInteractionContext & 0x80000000) != 0LL
          || (*a2 != 0.0 ? (v13 = DWORD1(v20) | 4) : (v13 = DWORD1(v20) & 0xFFFFFFFB),
              a2[1] != 0.0 && a2[2] != 0.0 ? (v14 = v13 | 8) : (v14 = v13 & 0xFFFFFFF7),
              a2[3] != 0.0 ? (v15 = v14 | 0x10) : (v15 = v14 & 0xFFFFFFEF),
              v16 = *(_QWORD *)(a1 + 296),
              DWORD1(v20) = v15,
              InteractionConfigurationInteractionContext = (unsigned int)SetInteractionConfigurationInteractionContext(
                                                                           v16,
                                                                           1,
                                                                           &v20),
              TouchWinRT::OnErrorOriginateError((TouchWinRT *)InteractionConfigurationInteractionContext, v17),
              (InteractionConfigurationInteractionContext & 0x80000000) != 0LL) )
        {
          v18 = *(_OWORD *)(a1 + 520);
          v19[0] = 4;
          v21 = v18;
          if ( (int)Windows::UI::Input::GestureRecognizerServer::ConvertCrossSlideValuesToIC(a1, &v21, v22, v19) >= 0 )
            SetCrossSlideParametersInteractionContext(*(_QWORD *)(a1 + 296), v19[0], v22);
        }
        else
        {
          *(_OWORD *)(a1 + 520) = *(_OWORD *)a2;
        }
      }
    }
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)InteractionConfigurationInteractionContext;
  }
}

```

## disassembly

```asm
0x1800adb70  mov     rax, rsp
0x1800adb73  mov     [rax+18h], rbx
0x1800adb77  mov     [rax+20h], rsi
0x1800adb7b  push    rbp
0x1800adb7c  push    rdi
0x1800adb7d  push    r14
0x1800adb7f  lea     rbp, [rax-5Fh]
0x1800adb83  sub     rsp, 90h
0x1800adb8a  movaps  xmmword ptr [rax-28h], xmm6
0x1800adb8e  mov     rax, cs:__security_cookie
0x1800adb95  xor     rax, rsp
0x1800adb98  mov     [rbp+57h+var_30], rax
0x1800adb9c  lea     r14, [rcx+248h]
0x1800adba3  mov     rbx, rcx
0x1800adba6  mov     rcx, r14; lpCriticalSection
0x1800adba9  mov     rsi, rdx
0x1800adbac  call    cs:__imp_EnterCriticalSection
0x1800adbb2  btr     dword ptr [rbx+240h], 8
0x1800adbba  or      eax, 0FFFFFFFFh
0x1800adbbd  mov     rcx, rbx; this
0x1800adbc0  mov     [rbp+57h+var_50], eax
0x1800adbc3  mov     [rbp+57h+var_48], eax
0x1800adbc6  xorps   xmm6, xmm6
0x1800adbc9  mov     [rbp+57h+var_40], eax
0x1800adbcc  mov     [rbp+57h+var_38], eax
0x1800adbcf  mov     [rbp+57h+var_80], 4
0x1800adbd6  mov     [rbp+57h+var_4C], 0
0x1800adbdd  mov     [rbp+57h+var_44], 0
0x1800adbe4  mov     [rbp+57h+var_3C], 0
0x1800adbeb  mov     [rbp+57h+var_34], 0
0x1800adbf2  call    ?MustCacheSettings@GestureRecognizerServer@Input@UI@Windows@@AEAAHXZ; Windows::UI::Input::GestureRecognizerServer::MustCacheSettings(void)
0x1800adbf7  movups  xmm0, xmmword ptr [rsi]
0x1800adbfa  test    eax, eax
0x1800adbfc  jz      short loc_1800ADC23
0x1800adbfe  bts     dword ptr [rbx+240h], 8
0x1800adc06  movdqu  xmmword ptr [rbx+208h], xmm0
0x1800adc0e  test    r14, r14
0x1800adc11  jz      short loc_1800ADC1C
0x1800adc13  mov     rcx, r14; lpCriticalSection
0x1800adc16  call    cs:__imp_LeaveCriticalSection
0x1800adc1c  xor     eax, eax
0x1800adc1e  jmp     loc_1800ADD66
0x1800adc23  lea     r9, [rbp+57h+var_80]
0x1800adc27  lea     r8, [rbp+57h+var_50]
0x1800adc2b  lea     rdx, [rbp+57h+var_70]
0x1800adc2f  movdqu  [rbp+57h+var_70], xmm0
0x1800adc34  call    ?ConvertCrossSlideValuesToIC@GestureRecognizerServer@Input@UI@Windows@@AEAAJUCrossSlideThresholds@234@PEAUCROSS_SLIDE_PARAMETER@@AEAI@Z; Windows::UI::Input::GestureRecognizerServer::ConvertCrossSlideValuesToIC(Windows::UI::Input::CrossSlideThresholds,CROSS_SLIDE_PARAMETER *,uint &)
0x1800adc39  mov     edi, eax
0x1800adc3b  test    eax, eax
0x1800adc3d  js      loc_1800ADD56
0x1800adc43  mov     edx, [rbp+57h+var_80]
0x1800adc46  lea     r8, [rbp+57h+var_50]
0x1800adc4a  mov     rcx, [rbx+128h]
0x1800adc51  call    cs:__imp_SetCrossSlideParametersInteractionContext
0x1800adc57  mov     ecx, eax; this
0x1800adc59  mov     edi, eax
0x1800adc5b  call    ?OnErrorOriginateError@TouchWinRT@@YAJJ@Z; TouchWinRT::OnErrorOriginateError(long)
0x1800adc60  test    edi, edi
0x1800adc62  js      loc_1800ADD56
0x1800adc68  mov     rcx, [rbx+128h]
0x1800adc6f  lea     r8, [rbp+57h+var_70]
0x1800adc73  mov     edx, 1
0x1800adc78  mov     qword ptr [rbp+57h+var_70], 6
0x1800adc80  call    cs:__imp_GetInteractionConfigurationInteractionContext
0x1800adc86  mov     ecx, eax; this
0x1800adc88  mov     edi, eax
0x1800adc8a  call    ?OnErrorOriginateError@TouchWinRT@@YAJJ@Z; TouchWinRT::OnErrorOriginateError(long)
0x1800adc8f  test    edi, edi
0x1800adc91  js      loc_1800ADD17
0x1800adc97  movss   xmm0, dword ptr [rsi]
0x1800adc9b  ucomiss xmm0, xmm6
0x1800adc9e  jp      short loc_1800ADCAA
0x1800adca0  jnz     short loc_1800ADCAA
0x1800adca2  mov     eax, dword ptr [rbp+57h+var_70+4]
0x1800adca5  and     eax, 0FFFFFFFBh
0x1800adca8  jmp     short loc_1800ADCB0
0x1800adcaa  mov     eax, dword ptr [rbp+57h+var_70+4]
0x1800adcad  or      eax, 4
0x1800adcb0  movss   xmm0, dword ptr [rsi+4]
0x1800adcb5  ucomiss xmm0, xmm6
0x1800adcb8  jp      short loc_1800ADCBC
0x1800adcba  jz      short loc_1800ADCC8
0x1800adcbc  movss   xmm0, dword ptr [rsi+8]
0x1800adcc1  ucomiss xmm0, xmm6
0x1800adcc4  jp      short loc_1800ADCCD
0x1800adcc6  jnz     short loc_1800ADCCD
0x1800adcc8  and     eax, 0FFFFFFF7h
0x1800adccb  jmp     short loc_1800ADCD0
0x1800adccd  or      eax, 8
0x1800adcd0  movss   xmm0, dword ptr [rsi+0Ch]
0x1800adcd5  ucomiss xmm0, xmm6
0x1800adcd8  jp      short loc_1800ADCE1
0x1800adcda  jnz     short loc_1800ADCE1
0x1800adcdc  and     eax, 0FFFFFFEFh
0x1800adcdf  jmp     short loc_1800ADCE4
0x1800adce1  or      eax, 10h
0x1800adce4  mov     rcx, [rbx+128h]
0x1800adceb  lea     r8, [rbp+57h+var_70]
0x1800adcef  mov     edx, 1
0x1800adcf4  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800adcf7  call    cs:__imp_SetInteractionConfigurationInteractionContext
0x1800adcfd  mov     ecx, eax; this
0x1800adcff  mov     edi, eax
0x1800add01  call    ?OnErrorOriginateError@TouchWinRT@@YAJJ@Z; TouchWinRT::OnErrorOriginateError(long)
0x1800add06  test    edi, edi
0x1800add08  js      short loc_1800ADD17
0x1800add0a  movups  xmm0, xmmword ptr [rsi]
0x1800add0d  movdqu  xmmword ptr [rbx+208h], xmm0
0x1800add15  jmp     short loc_1800ADD56
0x1800add17  movups  xmm0, xmmword ptr [rbx+208h]
0x1800add1e  lea     r9, [rbp+57h+var_80]
0x1800add22  mov     [rbp+57h+var_80], 4
0x1800add29  lea     r8, [rbp+57h+var_50]
0x1800add2d  mov     rcx, rbx
0x1800add30  lea     rdx, [rbp+57h+var_60]
0x1800add34  movdqu  [rbp+57h+var_60], xmm0
0x1800add39  call    ?ConvertCrossSlideValuesToIC@GestureRecognizerServer@Input@UI@Windows@@AEAAJUCrossSlideThresholds@234@PEAUCROSS_SLIDE_PARAMETER@@AEAI@Z; Windows::UI::Input::GestureRecognizerServer::ConvertCrossSlideValuesToIC(Windows::UI::Input::CrossSlideThresholds,CROSS_SLIDE_PARAMETER *,uint &)
0x1800add3e  test    eax, eax
0x1800add40  js      short loc_1800ADD56
0x1800add42  mov     edx, [rbp+57h+var_80]
0x1800add45  lea     r8, [rbp+57h+var_50]
0x1800add49  mov     rcx, [rbx+128h]
0x1800add50  call    cs:__imp_SetCrossSlideParametersInteractionContext
0x1800add56  test    r14, r14
0x1800add59  jz      short loc_1800ADD64
0x1800add5b  mov     rcx, r14; lpCriticalSection
0x1800add5e  call    cs:__imp_LeaveCriticalSection
0x1800add64  mov     eax, edi
0x1800add66  mov     rcx, [rbp+57h+var_30]
0x1800add6a  xor     rcx, rsp; StackCookie
0x1800add6d  call    __security_check_cookie
0x1800add72  lea     r11, [rsp+0A0h+var_10]
0x1800add7a  mov     rbx, [r11+30h]
0x1800add7e  mov     rsi, [r11+38h]
0x1800add82  movaps  xmm6, xmmword ptr [r11-10h]
0x1800add87  mov     rsp, r11
0x1800add8a  pop     r14
0x1800add8c  pop     rdi
0x1800add8d  pop     rbp
0x1800add8e  retn
```
