# I_DeleteKeyMaterial

- ea: `0x180020040`
- end: `0x1800201e7`
- name: `I_DeleteKeyMaterial`
- size: `423`
- prototype: `__int64 __fastcall(struct VCARD_DATA *, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001fd8c`
- `0x180023a38`
- `0x180023e54`
- `0x180024378`
- `0x180024aac`

## callees

- `0x180001ec0`
- `0x18000bc48`
- `0x18000c124`
- `0x18000c198`
- `0x18000fcb0`
- `0x18001cdbc`
- `0x18001df20`
- `0x180020040`
- `0x1800201f0`
- `0x1800348a0`

## string_xrefs

- `0x180020077`: `I_DeleteKeyMaterial`
- `0x1800201b4`: `Unable to delete asymmetric key`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_DeleteKeyMaterial(struct VCARD_DATA *a1, const struct KEY_MAP_RECORD *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // r9d
  unsigned int v8; // ebx
  __int64 v10; // rcx
  unsigned int v11; // [rsp+30h] [rbp-50h] BYREF
  int v12; // [rsp+34h] [rbp-4Ch] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v14[3]; // [rsp+40h] [rbp-40h] BYREF
  char v15[24]; // [rsp+58h] [rbp-28h] BYREF

  v11 = 0;
  v12 = 0;
  strcpy(v15, "I_DeleteKeyMaterial");
  v14[0] = v15;
  v14[1] = &v12;
  v14[2] = &v11;
  lambda_8c76bb2f8d99cdca7f4e6ebc57ac24a8_::operator()(v14);
  v12 = 1;
  v13 = v14;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5, v4);
  if ( !I_KeyMapIsActive(a2) )
    goto LABEL_20;
  if ( *((_DWORD *)a2 + 20) != 1 )
  {
    v6 = (unsigned int)(*((_DWORD *)a2 + 20) - 2);
    if ( (unsigned int)v6 >= 2 )
    {
      WppTraceIndent(v6, 2u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
            v7,
            13);
      }
      __fastfail(0xDu);
    }
  }
  v11 = I_DeleteKspKey(a1, (const unsigned __int16 *)a2);
  if ( v11 )
  {
    WppTraceIndent(v10, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sDs(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        (unsigned int)WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids,
        (_DWORD)WPP_pszIndent,
        v11,
        (__int64)"Unable to delete asymmetric key");
    }
LABEL_20:
    v8 = v11;
    goto LABEL_14;
  }
  v8 = 0;
LABEL_14:
  WppTraceUnwinder__lambda_8c76bb2f8d99cdca7f4e6ebc57ac24a8____::_WppTraceUnwinder__lambda_8c76bb2f8d99cdca7f4e6ebc57ac24a8____(&v13);
  return v8;
}

```

## disassembly

```asm
0x180020040  mov     [rsp-8+arg_10], rbx
0x180020045  mov     [rsp-8+arg_18], rdi
0x18002004a  push    rbp
0x18002004b  mov     rbp, rsp
0x18002004e  sub     rsp, 80h
0x180020055  mov     rax, cs:__security_cookie
0x18002005c  xor     rax, rsp
0x18002005f  mov     [rbp+var_10], rax
0x180020063  mov     rbx, rdx
0x180020066  mov     rdi, rcx
0x180020069  mov     [rbp+var_50], 0
0x180020070  mov     [rbp+var_4C], 0
0x180020077  movups  xmm0, xmmword ptr cs:aIDeletekeymate; "I_DeleteKeyMaterial"
0x18002007e  movups  xmmword ptr [rbp+var_28], xmm0
0x180020082  mov     eax, dword ptr cs:aIDeletekeymate+10h; "ial"
0x180020088  mov     dword ptr [rbp+var_28+10h], eax
0x18002008b  lea     rax, [rbp+var_28]
0x18002008f  mov     [rbp+var_40], rax
0x180020093  lea     rax, [rbp+var_4C]
0x180020097  mov     [rbp+var_38], rax
0x18002009b  lea     rax, [rbp+var_50]
0x18002009f  mov     [rbp+var_30], rax
0x1800200a3  lea     rcx, [rbp+var_40]
0x1800200a7  call    _lambda_8c76bb2f8d99cdca7f4e6ebc57ac24a8___operator__
0x1800200ac  mov     [rbp+var_4C], 1
0x1800200b3  lea     rax, [rbp+var_40]
0x1800200b7  mov     [rbp+var_48], rax
0x1800200bb  test    rdi, rdi
0x1800200be  jnz     short loc_1800200C5
0x1800200c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800200c5  test    rbx, rbx
0x1800200c8  jnz     short loc_1800200CF
0x1800200ca  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800200cf  mov     rcx, rbx; struct KEY_MAP_RECORD *
0x1800200d2  call    ?I_KeyMapIsActive@@YAHPEBUKEY_MAP_RECORD@@@Z; I_KeyMapIsActive(KEY_MAP_RECORD const *)
0x1800200d7  test    eax, eax
0x1800200d9  jz      loc_1800201DE
0x1800200df  mov     ecx, [rbx+50h]
0x1800200e2  sub     ecx, 1
0x1800200e5  jz      loc_180020174
0x1800200eb  sub     ecx, 1
0x1800200ee  jz      loc_180020174
0x1800200f4  cmp     ecx, 1
0x1800200f7  jz      short loc_180020174
0x1800200f9  mov     edx, 2
0x1800200fe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020103  lea     rax, WPP_GLOBAL_Control
0x18002010a  mov     ebx, 0Dh
0x18002010f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020116  cmp     rcx, rax
0x180020119  jz      short loc_18002013E
0x18002011b  test    byte ptr [rcx+1Ch], 1
0x18002011f  jz      short loc_18002013E
0x180020121  cmp     byte ptr [rcx+19h], 1
0x180020125  jb      short loc_18002013E
0x180020127  lea     edx, [rbx+31h]
0x18002012a  mov     [rsp+80h+var_60], ebx
0x18002012e  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x180020135  mov     rcx, [rcx+10h]
0x180020139  call    WPP_SF_sD
0x18002013e  mov     rcx, rbx
0x180020141  int     29h; Win8: RtlFailFast(ecx)
0x180020143  mov     eax, [rbp+var_50]
0x180020146  mov     ebx, eax
0x180020148  lea     rcx, [rbp+var_48]
0x18002014c  call    WppTraceUnwinder__lambda_8c76bb2f8d99cdca7f4e6ebc57ac24a8_______WppTraceUnwinder__lambda_8c76bb2f8d99cdca7f4e6ebc57ac24a8____
0x180020151  mov     eax, ebx
0x180020153  mov     rcx, [rbp+var_10]
0x180020157  xor     rcx, rsp; StackCookie
0x18002015a  call    __security_check_cookie
0x18002015f  lea     r11, [rsp+80h+var_s0]
0x180020167  mov     rbx, [r11+20h]
0x18002016b  mov     rdi, [r11+28h]
0x18002016f  mov     rsp, r11
0x180020172  pop     rbp
0x180020173  retn
0x180020174  mov     rdx, rbx; unsigned __int16 *
0x180020177  mov     rcx, rdi; struct VCARD_DATA *
0x18002017a  call    ?I_DeleteKspKey@@YAKPEBUVCARD_DATA@@PEBG@Z; I_DeleteKspKey(VCARD_DATA const *,ushort const *)
0x18002017f  mov     [rbp+var_50], eax
0x180020182  test    eax, eax
0x180020184  jz      short loc_180020146
0x180020186  mov     edx, 2
0x18002018b  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180020190  lea     rax, WPP_GLOBAL_Control
0x180020197  mov     rcx, cs:WPP_GLOBAL_Control
0x18002019e  cmp     rcx, rax
0x1800201a1  jz      short loc_1800201DE
0x1800201a3  test    byte ptr [rcx+1Ch], 1
0x1800201a7  jz      short loc_1800201DE
0x1800201a9  cmp     byte ptr [rcx+19h], 2
0x1800201ad  jb      short loc_1800201DE
0x1800201af  mov     edx, 3Dh ; '='
0x1800201b4  lea     rax, aUnableToDelete; "Unable to delete asymmetric key"
0x1800201bb  mov     [rsp+80h+var_58], rax
0x1800201c0  mov     eax, [rbp+var_50]
0x1800201c3  mov     [rsp+80h+var_60], eax
0x1800201c7  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800201ce  lea     r8, WPP_ea4669cd28db3200c02309d6e6ed7064_Traceguids
0x1800201d5  mov     rcx, [rcx+10h]
0x1800201d9  call    WPP_SF_sDs
0x1800201de  mov     ebx, [rbp+var_50]
0x1800201e1  jmp     loc_180020148
```
