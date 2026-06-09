# HUBREG_DeleteUxdDeviceKey

- ea: `0x140085504`
- end: `0x140085662`
- name: `HUBREG_DeleteUxdDeviceKey`
- size: `350`
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
- `0x140085504`

## pseudocode

```c
__int64 __fastcall HUBREG_DeleteUxdDeviceKey(__int64 a1)
{
  NTSTATUS v2; // ebx
  int v3; // edx
  __int64 v5; // [rsp+20h] [rbp-88h]
  __int64 v6; // [rsp+28h] [rbp-80h]
  __int64 v7; // [rsp+40h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-60h] BYREF
  __int64 v9; // [rsp+58h] [rbp-50h] BYREF

  *(_QWORD *)&DestinationString.Length = 3407872;
  DestinationString.Buffer = (wchar_t *)&v9;
  v7 = 0;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
         WdfDriverGlobals,
         0,
         &g_UxdDeviceSettingsKey,
         131097,
         0,
         &v7);
  if ( v2 >= 0 )
  {
    LODWORD(v5) = *(unsigned __int16 *)(a1 + 2008);
    v2 = RtlUnicodeStringPrintf(
           &DestinationString,
           L"%04X%04X%04X",
           *(unsigned __int16 *)(a1 + 2004),
           *(unsigned __int16 *)(a1 + 2006),
           v5);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1872))(
             WdfDriverGlobals,
             v7,
             &DestinationString);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v6) = v2;
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1432LL),
        v3,
        5,
        105,
        (__int64)WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids,
        v6);
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1848))(WdfDriverGlobals);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140085504  mov     r11, rsp
0x140085507  mov     [r11+10h], rbx
0x14008550b  push    rdi
0x14008550c  sub     rsp, 0A0h
0x140085513  mov     rax, cs:__security_cookie
0x14008551a  xor     rax, rsp
0x14008551d  mov     [rsp+0A8h+var_18], rax
0x140085525  lea     rax, [r11-50h]
0x140085529  mov     qword ptr [r11-60h], 340000h
0x140085531  mov     [r11-58h], rax
0x140085535  lea     r8, g_UxdDeviceSettingsKey
0x14008553c  mov     rax, cs:WdfFunctions_01015
0x140085543  mov     rdi, rcx
0x140085546  lea     rcx, [r11-68h]
0x14008554a  mov     qword ptr [r11-68h], 0
0x140085552  mov     [r11-80h], rcx
0x140085556  mov     r9d, 20019h
0x14008555c  mov     rcx, cs:WdfDriverGlobals
0x140085563  xor     edx, edx
0x140085565  mov     rax, [rax+728h]
0x14008556c  mov     [rsp+0A8h+var_88], 0
0x140085575  call    _guard_dispatch_icall
0x14008557a  mov     ebx, eax
0x14008557c  test    eax, eax
0x14008557e  js      loc_14008561A
0x140085584  movzx   eax, word ptr [rdi+7D8h]
0x14008558b  lea     rdx, a04x04x04x; "%04X%04X%04X"
0x140085592  movzx   r9d, word ptr [rdi+7D6h]
0x14008559a  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x14008559f  movzx   r8d, word ptr [rdi+7D4h]
0x1400855a7  mov     dword ptr [rsp+0A8h+var_88], eax
0x1400855ab  call    RtlUnicodeStringPrintf
0x1400855b0  mov     ebx, eax
0x1400855b2  test    eax, eax
0x1400855b4  jns     short loc_1400855F4
0x1400855b6  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400855bd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400855c4  jz      short loc_14008561A
0x1400855c6  mov     rcx, [rdi+8]
0x1400855ca  lea     rax, WPP_fe827790944537bbfef1c01f2ab82bc9_Traceguids
0x1400855d1  mov     r9d, 69h ; 'i'
0x1400855d7  mov     dword ptr [rsp+0A8h+var_80], ebx
0x1400855db  mov     dl, 2
0x1400855dd  mov     [rsp+0A8h+var_88], rax
0x1400855e2  mov     rcx, [rcx+598h]
0x1400855e9  lea     r8d, [r9-64h]
0x1400855ed  call    WPP_RECORDER_SF_d
0x1400855f2  jmp     short loc_14008561A
0x1400855f4  mov     rax, cs:WdfFunctions_01015
0x1400855fb  lea     r8, [rsp+0A8h+DestinationString]
0x140085600  mov     rdx, [rsp+0A8h+var_68]
0x140085605  mov     rcx, cs:WdfDriverGlobals
0x14008560c  mov     rax, [rax+750h]
0x140085613  call    _guard_dispatch_icall
0x140085618  mov     ebx, eax
0x14008561a  mov     rdx, [rsp+0A8h+var_68]
0x14008561f  test    rdx, rdx
0x140085622  jz      short loc_14008563E
0x140085624  mov     rax, cs:WdfFunctions_01015
0x14008562b  mov     rcx, cs:WdfDriverGlobals
0x140085632  mov     rax, [rax+738h]
0x140085639  call    _guard_dispatch_icall
0x14008563e  mov     eax, ebx
0x140085640  mov     rcx, [rsp+0A8h+var_18]
0x140085648  xor     rcx, rsp; StackCookie
0x14008564b  call    __security_check_cookie
0x140085650  mov     rbx, [rsp+0A8h+arg_8]
0x140085658  add     rsp, 0A0h
0x14008565f  pop     rdi
0x140085660  retn
```
