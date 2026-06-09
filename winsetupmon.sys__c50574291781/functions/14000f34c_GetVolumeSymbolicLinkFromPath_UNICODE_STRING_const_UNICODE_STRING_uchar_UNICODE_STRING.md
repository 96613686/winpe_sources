# GetVolumeSymbolicLinkFromPath(_UNICODE_STRING const *,_UNICODE_STRING *,uchar *,_UNICODE_STRING *)

- ea: `0x14000f34c`
- end: `0x14000f67c`
- name: `?GetVolumeSymbolicLinkFromPath@@YAJPEBU_UNICODE_STRING@@PEAU1@PEAE1@Z`
- size: `816`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2, PUNICODE_STRING DestinationString, unsigned __int8 *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x14000e1d0`

## callees

- `0x14000dd24`
- `0x14000eb68`
- `0x14000f34c`
- `0x14000f900`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f4f4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f549`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f5f4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f4f4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f549`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000f5f4`

## pseudocode

```c
__int64 __fastcall GetVolumeSymbolicLinkFromPath(
        PCUNICODE_STRING String2,
        PUNICODE_STRING DestinationString,
        unsigned __int8 *a3,
        struct _UNICODE_STRING *a4)
{
  unsigned __int16 Length; // r9
  unsigned __int8 v9; // si
  wchar_t *Buffer; // rdx
  unsigned __int16 v11; // ax
  wchar_t *v12; // rcx
  wchar_t v13; // ax
  wchar_t v14; // dx
  unsigned int v15; // ecx
  UNICODE_STRING v16; // xmm0
  unsigned __int16 v17; // ax
  __int64 result; // rax
  wchar_t *v19; // rcx
  __int64 v20; // xmm0_8
  wchar_t *v21; // rax
  wchar_t *v22; // rcx
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-99h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-89h] BYREF
  UNICODE_STRING String2a; // [rsp+40h] [rbp-79h] BYREF
  __int64 v26; // [rsp+50h] [rbp-69h] BYREF
  int v27; // [rsp+58h] [rbp-61h]
  wchar_t v28; // [rsp+5Ch] [rbp-5Dh]
  __int128 v29; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v30[80]; // [rsp+70h] [rbp-49h]
  wchar_t v31; // [rsp+C0h] [rbp+7h]

  Length = String2->Length;
  v26 = *(_QWORD *)L"\\??\\?:";
  v27 = *(_DWORD *)L"?:";
  v9 = 1;
  *(_OWORD *)v30 = *(_OWORD *)L"me{00000000-0000-0000-0000-000000000000}";
  v28 = asc_140016CB0[6];
  *(_OWORD *)&v30[32] = *(_OWORD *)L"-0000-0000-000000000000}";
  v31 = aVolume00000000[48];
  *(_OWORD *)&v30[64] = *(_OWORD *)L"0000000}";
  *(_QWORD *)&String1.Length = 1966108;
  String1.Buffer = L"\\\\?\\GLOBALROOT";
  SourceString = 0;
  v29 = *(_OWORD *)L"\\??\\Volume{00000000-0000-0000-0000-000000000000}";
  *(_OWORD *)&v30[16] = *(_OWORD *)L"000-0000-0000-0000-000000000000}";
  *(_OWORD *)&v30[48] = *(_OWORD *)L"00-000000000000}";
  if ( Length >= 4u )
  {
    Buffer = String2->Buffer;
    if ( ((unsigned __int16)(*Buffer - 97) <= 0x19u || (unsigned __int16)(*Buffer - 65) <= 0x19u) && Buffer[1] == 58 )
    {
      *(_QWORD *)&SourceString.Length = 917516;
      SourceString.Buffer = (wchar_t *)&v26;
      LOWORD(v27) = *Buffer;
      a4->Buffer = Buffer + 2;
      v11 = String2->Length - 4;
      goto LABEL_23;
    }
  }
  if ( Length >= 0xCu )
  {
    v12 = String2->Buffer;
    if ( *v12 == 92 )
    {
      v13 = v12[1];
      if ( (v13 == 92 || v13 == 63) && v12[2] == 63 && v12[3] == 92 )
      {
        v14 = v12[4];
        if ( ((unsigned __int16)(v14 - 97) <= 0x19u || (unsigned __int16)(v14 - 65) <= 0x19u) && v12[5] == 58 )
        {
          *(_QWORD *)&SourceString.Length = 917516;
          SourceString.Buffer = (wchar_t *)&v26;
          LOWORD(v27) = v12[4];
          a4->Buffer = v12 + 6;
          v11 = String2->Length - 12;
          goto LABEL_23;
        }
      }
    }
  }
  if ( RtlPrefixUnicodeString(&stru_140012420, String2, 1u) )
  {
    v15 = 0;
    if ( String2->Length >= 0x60u )
    {
      v16 = *String2;
      a4->Buffer = String2->Buffer + 48;
      v17 = String2->Length - 96;
      SourceString = v16;
      a4->MaximumLength = v17;
      a4->Length = v17;
      *(_DWORD *)&SourceString.Length = 6291552;
LABEL_27:
      v9 = 0;
      *DestinationString = SourceString;
      goto LABEL_28;
    }
    return 3221225529LL;
  }
  if ( !RtlPrefixUnicodeString(&::String1, String2, 1u) )
  {
    if ( !RtlPrefixUnicodeString(&String1, String2, 1u) )
      return 3221225659LL;
    v21 = String2->Buffer;
    String2a = 0;
    v22 = &v21[(unsigned __int64)String1.Length >> 1];
    LOWORD(v21) = String2->Length - String1.Length;
    String2a.Buffer = v22;
    String2a.MaximumLength = (unsigned __int16)v21;
    String2a.Length = (unsigned __int16)v21;
    result = GetVolumeDeviceInPath(&String2a, &SourceString, a4);
    v15 = result;
    if ( (int)result < 0 )
      return result;
    goto LABEL_27;
  }
  if ( String2->Length < 0x60u )
    return 3221225529LL;
  v19 = String2->Buffer;
  SourceString.Buffer = (wchar_t *)&v29;
  *(_QWORD *)&SourceString.Length = 6422624;
  *(_OWORD *)&v30[6] = *(_OWORD *)(v19 + 11);
  *(_OWORD *)&v30[22] = *(_OWORD *)(v19 + 19);
  *(_OWORD *)&v30[38] = *(_OWORD *)(v19 + 27);
  *(_OWORD *)&v30[54] = *(_OWORD *)(v19 + 35);
  v20 = *(_QWORD *)(v19 + 43);
  a4->Buffer = v19 + 48;
  v11 = String2->Length - 96;
  *(_QWORD *)&v30[70] = v20;
LABEL_23:
  a4->MaximumLength = v11;
  a4->Length = v11;
  result = Duplicate(&SourceString, DestinationString);
  v15 = result;
  if ( (int)result >= 0 )
  {
LABEL_28:
    *a3 = v9;
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x14000f34c  push    rbp
0x14000f34e  push    rbx
0x14000f34f  push    rsi
0x14000f350  push    rdi
0x14000f351  push    r14
0x14000f353  push    r15
0x14000f355  lea     rbp, [rsp-2Fh]
0x14000f35a  sub     rsp, 0E8h
0x14000f361  mov     rax, cs:__security_cookie
0x14000f368  xor     rax, rsp
0x14000f36b  mov     [rbp+57h+var_40], rax
0x14000f36f  mov     eax, dword ptr cs:asc_140016CB0+8; "?:"
0x14000f375  xorps   xmm0, xmm0
0x14000f378  movsd   xmm1, qword ptr cs:asc_140016CB0; "\\??\\?:"
0x14000f380  mov     rdi, r9
0x14000f383  movzx   r9d, word ptr [rcx]
0x14000f387  mov     r15, r8
0x14000f38a  movsd   [rbp+57h+var_C0], xmm1
0x14000f38f  mov     r14, rdx
0x14000f392  movaps  xmm1, xmmword ptr cs:aVolume00000000+10h; "me{00000000-0000-0000-0000-000000000000"...
0x14000f399  mov     rbx, rcx
0x14000f39c  mov     [rbp+57h+var_B8], eax
0x14000f39f  mov     sil, 1
0x14000f3a2  movzx   eax, word ptr cs:asc_140016CB0+0Ch; ""
0x14000f3a9  mov     r10w, 19h
0x14000f3ae  movaps  [rbp+57h+var_A0], xmm1
0x14000f3b2  movaps  xmm1, xmmword ptr cs:aVolume00000000+30h; "-0000-0000-000000000000}"
0x14000f3b9  mov     [rbp+57h+var_B4], ax
0x14000f3bd  movzx   eax, word ptr cs:aVolume00000000+60h; ""
0x14000f3c4  movaps  [rbp+57h+var_80], xmm1
0x14000f3c8  movaps  xmm1, xmmword ptr cs:aVolume00000000+50h; "0000000}"
0x14000f3cf  mov     [rbp+57h+var_50], ax
0x14000f3d3  lea     rax, aGlobalroot; "\\\\?\\GLOBALROOT"
0x14000f3da  movaps  [rbp+57h+var_60], xmm1
0x14000f3de  mov     qword ptr [rsp+110h+String1.Length], 1E001Ch
0x14000f3e7  mov     [rsp+110h+String1.Buffer], rax
0x14000f3ec  movups  xmmword ptr [rsp+110h+SourceString.Length], xmm0
0x14000f3f1  movaps  xmm0, xmmword ptr cs:aVolume00000000; "\\??\\Volume{00000000-0000-0000-0000-00"...
0x14000f3f8  movaps  [rbp+57h+var_B0], xmm0
0x14000f3fc  movaps  xmm0, xmmword ptr cs:aVolume00000000+20h; "000-0000-0000-0000-000000000000}"
0x14000f403  movaps  [rbp+57h+var_90], xmm0
0x14000f407  movaps  xmm0, xmmword ptr cs:aVolume00000000+40h; "00-000000000000}"
0x14000f40e  movaps  [rbp+57h+var_70], xmm0
0x14000f412  cmp     r9w, 4
0x14000f417  jb      short loc_14000F467
0x14000f419  mov     rdx, [rcx+8]
0x14000f41d  movzx   ecx, word ptr [rdx]
0x14000f420  lea     eax, [rcx-61h]
0x14000f423  cmp     ax, r10w
0x14000f427  jbe     short loc_14000F433
0x14000f429  sub     cx, 41h ; 'A'
0x14000f42d  cmp     cx, r10w
0x14000f431  ja      short loc_14000F467
0x14000f433  cmp     word ptr [rdx+2], 3Ah ; ':'
0x14000f438  jnz     short loc_14000F467
0x14000f43a  lea     rax, [rbp+57h+var_C0]
0x14000f43e  mov     qword ptr [rsp+110h+SourceString.Length], 0E000Ch
0x14000f447  mov     [rsp+110h+SourceString.Buffer], rax
0x14000f44c  movzx   eax, word ptr [rdx]
0x14000f44f  mov     word ptr [rbp+57h+var_B8], ax
0x14000f453  lea     rax, [rdx+4]
0x14000f457  mov     [rdi+8], rax
0x14000f45b  movzx   eax, word ptr [rbx]
0x14000f45e  sub     ax, 4
0x14000f462  jmp     loc_14000F5C5
0x14000f467  mov     r8d, 0Ch
0x14000f46d  cmp     r9w, r8w
0x14000f471  jb      short loc_14000F4E7
0x14000f473  mov     rcx, [rbx+8]
0x14000f477  cmp     word ptr [rcx], 5Ch ; '\'
0x14000f47b  jnz     short loc_14000F4E7
0x14000f47d  movzx   eax, word ptr [rcx+2]
0x14000f481  cmp     ax, 5Ch ; '\'
0x14000f485  jz      short loc_14000F48D
0x14000f487  cmp     ax, 3Fh ; '?'
0x14000f48b  jnz     short loc_14000F4E7
0x14000f48d  cmp     word ptr [rcx+4], 3Fh ; '?'
0x14000f492  jnz     short loc_14000F4E7
0x14000f494  cmp     word ptr [rcx+6], 5Ch ; '\'
0x14000f499  jnz     short loc_14000F4E7
0x14000f49b  movzx   edx, word ptr [rcx+8]
0x14000f49f  lea     eax, [rdx-61h]
0x14000f4a2  cmp     ax, r10w
0x14000f4a6  jbe     short loc_14000F4B2
0x14000f4a8  sub     dx, 41h ; 'A'
0x14000f4ac  cmp     dx, r10w
0x14000f4b0  ja      short loc_14000F4E7
0x14000f4b2  cmp     word ptr [rcx+0Ah], 3Ah ; ':'
0x14000f4b7  jnz     short loc_14000F4E7
0x14000f4b9  lea     rax, [rbp+57h+var_C0]
0x14000f4bd  mov     qword ptr [rsp+110h+SourceString.Length], 0E000Ch
0x14000f4c6  mov     [rsp+110h+SourceString.Buffer], rax
0x14000f4cb  movzx   eax, word ptr [rcx+8]
0x14000f4cf  mov     word ptr [rbp+57h+var_B8], ax
0x14000f4d3  lea     rax, [rcx+0Ch]
0x14000f4d7  mov     [rdi+8], rax
0x14000f4db  movzx   eax, word ptr [rbx]
0x14000f4de  sub     ax, r8w
0x14000f4e2  jmp     loc_14000F5C5
0x14000f4e7  mov     r8b, sil; CaseInSensitive
0x14000f4ea  lea     rcx, stru_140012420; String1
0x14000f4f1  mov     rdx, rbx; String2
0x14000f4f4  call    cs:__imp_RtlPrefixUnicodeString
0x14000f4fb  nop     dword ptr [rax+rax+00h]
0x14000f500  test    al, al
0x14000f502  jz      short loc_14000F53C
0x14000f504  xor     ecx, ecx
0x14000f506  lea     edx, [rcx+60h]
0x14000f509  cmp     [rbx], dx
0x14000f50c  jb      short loc_14000F567
0x14000f50e  mov     rax, [rbx+8]
0x14000f512  movups  xmm0, xmmword ptr [rbx]
0x14000f515  add     rax, rdx
0x14000f518  mov     [rdi+8], rax
0x14000f51c  movzx   eax, word ptr [rbx]
0x14000f51f  sub     ax, dx
0x14000f522  movdqu  xmmword ptr [rsp+110h+SourceString.Length], xmm0
0x14000f528  mov     [rdi+2], ax
0x14000f52c  mov     [rdi], ax
0x14000f52f  mov     dword ptr [rsp+110h+SourceString.Length], 600060h
0x14000f537  jmp     loc_14000F646
0x14000f53c  mov     r8b, sil; CaseInSensitive
0x14000f53f  lea     rcx, String1; String1
0x14000f546  mov     rdx, rbx; String2
0x14000f549  call    cs:__imp_RtlPrefixUnicodeString
0x14000f550  nop     dword ptr [rax+rax+00h]
0x14000f555  test    al, al
0x14000f557  jz      loc_14000F5E9
0x14000f55d  mov     edx, 60h ; '`'
0x14000f562  cmp     [rbx], dx
0x14000f565  jnb     short loc_14000F571
0x14000f567  mov     eax, 0C0000039h
0x14000f56c  jmp     loc_14000F65F
0x14000f571  mov     rcx, [rbx+8]
0x14000f575  lea     rax, [rbp+57h+var_B0]
0x14000f579  mov     [rsp+110h+SourceString.Buffer], rax
0x14000f57e  mov     rax, rdx
0x14000f581  mov     qword ptr [rsp+110h+SourceString.Length], 620060h
0x14000f58a  shr     rax, 1
0x14000f58d  movups  xmm0, xmmword ptr [rcx+16h]
0x14000f591  movups  [rbp+57h+var_A0+6], xmm0
0x14000f595  lea     rax, [rcx+rax*2]
0x14000f599  movups  xmm1, xmmword ptr [rcx+26h]
0x14000f59d  movups  [rbp+57h+var_90+6], xmm1
0x14000f5a1  movups  xmm0, xmmword ptr [rcx+36h]
0x14000f5a5  movups  [rbp+57h+var_80+6], xmm0
0x14000f5a9  movups  xmm1, xmmword ptr [rcx+46h]
0x14000f5ad  movups  [rbp+57h+var_70+6], xmm1
0x14000f5b1  movsd   xmm0, qword ptr [rcx+56h]
0x14000f5b6  mov     [rdi+8], rax
0x14000f5ba  movzx   eax, word ptr [rbx]
0x14000f5bd  sub     ax, dx
0x14000f5c0  movsd   qword ptr [rbp+57h+var_60+6], xmm0
0x14000f5c5  mov     ecx, 2
0x14000f5ca  mov     rdx, rdi
0x14000f5cd  mov     [rcx+rdi], ax
0x14000f5d1  lea     rcx, [rsp+110h+SourceString]; SourceString
0x14000f5d6  mov     [rdx], ax
0x14000f5d9  mov     rdx, r14; DestinationString
0x14000f5dc  call    ?Duplicate@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z; Duplicate(_UNICODE_STRING const *,_UNICODE_STRING *)
0x14000f5e1  mov     ecx, eax
0x14000f5e3  test    eax, eax
0x14000f5e5  jns     short loc_14000F653
0x14000f5e7  jmp     short loc_14000F65F
0x14000f5e9  mov     r8b, sil; CaseInSensitive
0x14000f5ec  lea     rcx, [rsp+110h+String1]; String1
0x14000f5f1  mov     rdx, rbx; String2
0x14000f5f4  call    cs:__imp_RtlPrefixUnicodeString
0x14000f5fb  nop     dword ptr [rax+rax+00h]
0x14000f600  test    al, al
0x14000f602  jz      short loc_14000F65A
0x14000f604  mov     rax, [rbx+8]
0x14000f608  lea     rdx, [rsp+110h+SourceString]; struct _UNICODE_STRING *
0x14000f60d  movzx   ecx, [rsp+110h+String1.Length]
0x14000f612  xorps   xmm0, xmm0
0x14000f615  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x14000f619  shr     rcx, 1
0x14000f61c  mov     r8, rdi; struct _UNICODE_STRING *
0x14000f61f  lea     rcx, [rax+rcx*2]
0x14000f623  movzx   eax, word ptr [rbx]
0x14000f626  sub     ax, [rsp+110h+String1.Length]
0x14000f62b  mov     [rbp+57h+String2.Buffer], rcx
0x14000f62f  lea     rcx, [rbp+57h+String2]; String2
0x14000f633  mov     [rbp+57h+String2.MaximumLength], ax
0x14000f637  mov     [rbp+57h+String2.Length], ax
0x14000f63b  call    ?GetVolumeDeviceInPath@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetVolumeDeviceInPath(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000f640  mov     ecx, eax
0x14000f642  test    eax, eax
0x14000f644  js      short loc_14000F65F
0x14000f646  movups  xmm0, xmmword ptr [rsp+110h+SourceString.Length]
0x14000f64b  xor     sil, sil
0x14000f64e  movdqu  xmmword ptr [r14], xmm0
0x14000f653  mov     [r15], sil
0x14000f656  mov     eax, ecx
0x14000f658  jmp     short loc_14000F65F
0x14000f65a  mov     eax, 0C00000BBh
0x14000f65f  mov     rcx, [rbp+57h+var_40]
0x14000f663  xor     rcx, rsp; StackCookie
0x14000f666  call    __security_check_cookie
0x14000f66b  add     rsp, 0E8h
0x14000f672  pop     r15
0x14000f674  pop     r14
0x14000f676  pop     rdi
0x14000f677  pop     rsi
0x14000f678  pop     rbx
0x14000f679  pop     rbp
0x14000f67a  retn
```
