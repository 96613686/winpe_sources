# HUBREG_DeleteUxdPortKey

- ea: `0x140085668`
- end: `0x1400858d0`
- name: `HUBREG_DeleteUxdPortKey`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400858d8`

## callees

- `0x1400024b8`
- `0x14000f648`
- `0x140045530`
- `0x140045570`
- `0x140085668`

## pseudocode

```c
__int64 __fastcall HUBREG_DeleteUxdPortKey(__int64 a1, unsigned int a2)
{
  __int64 v4; // rdx
  int v5; // edx
  NTSTATUS v6; // ebx
  int v7; // r9d
  __int64 v9; // [rsp+28h] [rbp-41h]
  __int64 v10; // [rsp+50h] [rbp-19h] BYREF
  __int64 v11; // [rsp+58h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-9h] BYREF
  char v13; // [rsp+70h] [rbp+7h] BYREF

  *(_QWORD *)&DestinationString.Length = 3670016;
  v10 = 0;
  DestinationString.Buffer = (wchar_t *)&v13;
  v4 = *(_QWORD *)(a1 + 16);
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 384))(
         WdfDriverGlobals,
         v4,
         1,
         983103,
         0,
         &v10);
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_16;
    v7 = 109;
    goto LABEL_4;
  }
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
         WdfDriverGlobals,
         v10,
         &g_UxdPortSettingsKey,
         983103,
         0,
         &v11);
  if ( v6 == -1073741772 )
  {
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *, __int64, _DWORD, _QWORD, _QWORD, __int64 *))(WdfFunctions_01015 + 1840))(
           WdfDriverGlobals,
           v10,
           &g_UxdPortSettingsKey,
           983103,
           0,
           0,
           0,
           &v11);
    if ( v6 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 110;
LABEL_4:
      LODWORD(v9) = v6;
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 2536), v5, 3, v7, (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids, v9);
    }
  }
  else if ( v6 >= 0 )
  {
    v6 = RtlUnicodeStringPrintf(&DestinationString, L"uxd_port_%3.3d", a2);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1872))(
             WdfDriverGlobals,
             v11,
             &DestinationString);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 112;
      goto LABEL_4;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = 111;
    goto LABEL_4;
  }
LABEL_16:
  if ( v10 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  if ( v11 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140085668  mov     [rsp-8+arg_10], rbx
0x14008566d  push    rbp
0x14008566e  push    rsi
0x14008566f  push    rdi
0x140085670  lea     rbp, [rsp-47h]
0x140085675  sub     rsp, 0B0h
0x14008567c  mov     rax, cs:__security_cookie
0x140085683  xor     rax, rsp
0x140085686  mov     [rbp+57h+var_18], rax
0x14008568a  mov     rdi, rcx
0x14008568d  mov     qword ptr [rbp+57h+DestinationString.Length], 380000h
0x140085695  lea     rax, [rbp+57h+var_50]
0x140085699  mov     [rbp+57h+var_70], 0
0x1400856a1  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400856a5  lea     rcx, [rbp+57h+var_70]
0x1400856a9  mov     rax, cs:WdfFunctions_01015
0x1400856b0  mov     esi, edx
0x1400856b2  mov     rdx, [rdi+10h]
0x1400856b6  mov     r9d, 0F003Fh
0x1400856bc  mov     [rsp+0C0h+var_98], rcx
0x1400856c1  mov     r8d, 1
0x1400856c7  mov     rcx, cs:WdfDriverGlobals
0x1400856ce  mov     [rbp+57h+var_68], 0
0x1400856d6  mov     rax, [rax+180h]
0x1400856dd  mov     [rsp+0C0h+var_A0], 0
0x1400856e6  call    _guard_dispatch_icall
0x1400856eb  mov     ebx, eax
0x1400856ed  test    eax, eax
0x1400856ef  jns     short loc_140085734
0x1400856f1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400856f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400856ff  jz      loc_140085868
0x140085705  mov     r9d, 6Dh ; 'm'
0x14008570b  mov     rcx, [rdi+9E8h]
0x140085712  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x140085719  mov     dword ptr [rsp+0C0h+var_98], ebx
0x14008571d  mov     r8d, 3
0x140085723  mov     dl, 2
0x140085725  mov     [rsp+0C0h+var_A0], rax
0x14008572a  call    WPP_RECORDER_SF_d
0x14008572f  jmp     loc_140085868
0x140085734  mov     rax, cs:WdfFunctions_01015
0x14008573b  lea     rcx, [rbp+57h+var_68]
0x14008573f  mov     rdx, [rbp+57h+var_70]
0x140085743  lea     r8, g_UxdPortSettingsKey
0x14008574a  mov     [rsp+0C0h+var_98], rcx
0x14008574f  mov     r9d, 0F003Fh
0x140085755  mov     rcx, cs:WdfDriverGlobals
0x14008575c  mov     rax, [rax+728h]
0x140085763  mov     [rsp+0C0h+var_A0], 0
0x14008576c  call    _guard_dispatch_icall
0x140085771  mov     ebx, eax
0x140085773  cmp     eax, 0C0000034h
0x140085778  jnz     short loc_1400857F1
0x14008577a  mov     rax, cs:WdfFunctions_01015
0x140085781  lea     rcx, [rbp+57h+var_68]
0x140085785  mov     rdx, [rbp+57h+var_70]
0x140085789  lea     r8, g_UxdPortSettingsKey
0x140085790  mov     [rsp+0C0h+var_88], rcx
0x140085795  mov     r9d, 0F003Fh
0x14008579b  mov     rcx, cs:WdfDriverGlobals
0x1400857a2  mov     rax, [rax+730h]
0x1400857a9  mov     [rsp+0C0h+var_90], 0
0x1400857b2  mov     [rsp+0C0h+var_98], 0
0x1400857bb  mov     dword ptr [rsp+0C0h+var_A0], 0
0x1400857c3  call    _guard_dispatch_icall
0x1400857c8  mov     ebx, eax
0x1400857ca  test    eax, eax
0x1400857cc  jns     loc_140085868
0x1400857d2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400857d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400857e0  jz      loc_140085868
0x1400857e6  mov     r9d, 6Eh ; 'n'
0x1400857ec  jmp     loc_14008570B
0x1400857f1  test    ebx, ebx
0x1400857f3  jns     short loc_140085810
0x1400857f5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400857fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140085803  jz      short loc_140085868
0x140085805  mov     r9d, 6Fh ; 'o'
0x14008580b  jmp     loc_14008570B
0x140085810  mov     r8d, esi
0x140085813  lea     rdx, aUxdPort33d; "uxd_port_%3.3d"
0x14008581a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14008581e  call    RtlUnicodeStringPrintf
0x140085823  mov     ebx, eax
0x140085825  test    eax, eax
0x140085827  jns     short loc_140085844
0x140085829  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140085830  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140085837  jz      short loc_140085868
0x140085839  mov     r9d, 70h ; 'p'
0x14008583f  jmp     loc_14008570B
0x140085844  mov     rax, cs:WdfFunctions_01015
0x14008584b  lea     r8, [rbp+57h+DestinationString]
0x14008584f  mov     rdx, [rbp+57h+var_68]
0x140085853  mov     rcx, cs:WdfDriverGlobals
0x14008585a  mov     rax, [rax+750h]
0x140085861  call    _guard_dispatch_icall
0x140085866  mov     ebx, eax
0x140085868  mov     rdx, [rbp+57h+var_70]
0x14008586c  test    rdx, rdx
0x14008586f  jz      short loc_14008588B
0x140085871  mov     rax, cs:WdfFunctions_01015
0x140085878  mov     rcx, cs:WdfDriverGlobals
0x14008587f  mov     rax, [rax+738h]
0x140085886  call    _guard_dispatch_icall
0x14008588b  mov     rdx, [rbp+57h+var_68]
0x14008588f  test    rdx, rdx
0x140085892  jz      short loc_1400858AE
0x140085894  mov     rax, cs:WdfFunctions_01015
0x14008589b  mov     rcx, cs:WdfDriverGlobals
0x1400858a2  mov     rax, [rax+738h]
0x1400858a9  call    _guard_dispatch_icall
0x1400858ae  mov     eax, ebx
0x1400858b0  mov     rcx, [rbp+57h+var_18]
0x1400858b4  xor     rcx, rsp; StackCookie
0x1400858b7  call    __security_check_cookie
0x1400858bc  mov     rbx, [rsp+0C0h+arg_10]
0x1400858c4  add     rsp, 0B0h
0x1400858cb  pop     rdi
0x1400858cc  pop     rsi
0x1400858cd  pop     rbp
0x1400858ce  retn
```
