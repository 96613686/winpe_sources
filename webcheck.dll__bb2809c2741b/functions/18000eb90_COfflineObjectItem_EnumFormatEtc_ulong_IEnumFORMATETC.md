# COfflineObjectItem::EnumFormatEtc(ulong,IEnumFORMATETC * *)

- ea: `0x18000eb90`
- end: `0x18000ec57`
- name: `?EnumFormatEtc@COfflineObjectItem@@UEAAJKPEAPEAUIEnumFORMATETC@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(COfflineObjectItem *__hidden this, unsigned int, struct IEnumFORMATETC **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180029280`

## import_xrefs

- `SHELL32!__imp_SHCreateStdEnumFmtEtc` at `0x18000ec3c`
- `SHELL32!__imp_SHCreateStdEnumFmtEtc` at `0x18000ec3c`

## pseudocode

```c
HRESULT __fastcall COfflineObjectItem::EnumFormatEtc(COfflineObjectItem *this, __int64 a2, struct IEnumFORMATETC **a3)
{
  FORMATETC afmt; // [rsp+20h] [rbp-59h] BYREF
  __int16 v5; // [rsp+40h] [rbp-39h]
  __int64 v6; // [rsp+48h] [rbp-31h]
  int v7; // [rsp+50h] [rbp-29h]
  int v8; // [rsp+54h] [rbp-25h]
  int v9; // [rsp+58h] [rbp-21h]
  __int16 v10; // [rsp+60h] [rbp-19h]
  __int64 v11; // [rsp+68h] [rbp-11h]
  int v12; // [rsp+70h] [rbp-9h]
  int v13; // [rsp+74h] [rbp-5h]
  int v14; // [rsp+78h] [rbp-1h]
  __int16 v15; // [rsp+80h] [rbp+7h]
  __int64 v16; // [rsp+88h] [rbp+Fh]
  int v17; // [rsp+90h] [rbp+17h]
  int v18; // [rsp+94h] [rbp+1Bh]
  int v19; // [rsp+98h] [rbp+1Fh]
  __int16 v20; // [rsp+A0h] [rbp+27h]
  __int64 v21; // [rsp+A8h] [rbp+2Fh]
  int v22; // [rsp+B0h] [rbp+37h]
  int v23; // [rsp+B4h] [rbp+3Bh]
  int v24; // [rsp+B8h] [rbp+3Fh]

  afmt.cfFormat = g_cfFileDescriptor;
  v5 = g_cfFileContents;
  v10 = g_cfPrefDropEffect;
  afmt.ptd = 0;
  afmt.lindex = -1;
  v6 = 0;
  v8 = -1;
  v11 = 0;
  v13 = -1;
  v16 = 0;
  v18 = -1;
  v21 = 0;
  v23 = -1;
  v15 = g_cfURL;
  afmt.dwAspect = 1;
  afmt.tymed = 1;
  v7 = 1;
  v9 = 4;
  v12 = 1;
  v14 = 1;
  v17 = 1;
  v19 = 1;
  v20 = 1;
  v22 = 1;
  v24 = 1;
  return SHCreateStdEnumFmtEtc(5u, &afmt, a3);
}

```

## disassembly

```asm
0x18000eb90  push    rbp
0x18000eb92  lea     rbp, [rsp-57h]
0x18000eb97  sub     rsp, 0D0h
0x18000eb9e  mov     rax, cs:__security_cookie
0x18000eba5  xor     rax, rsp
0x18000eba8  mov     [rbp+57h+var_10], rax
0x18000ebac  movzx   eax, word ptr cs:?g_cfFileDescriptor@@3IA; uint g_cfFileDescriptor
0x18000ebb3  xor     edx, edx
0x18000ebb5  or      ecx, 0FFFFFFFFh
0x18000ebb8  mov     [rbp+57h+afmt.cfFormat], ax
0x18000ebbc  movzx   eax, word ptr cs:?g_cfFileContents@@3IA; uint g_cfFileContents
0x18000ebc3  mov     [rbp+57h+var_90], ax
0x18000ebc7  movzx   eax, word ptr cs:?g_cfPrefDropEffect@@3IA; uint g_cfPrefDropEffect
0x18000ebce  lea     r9d, [rdx+1]
0x18000ebd2  mov     [rbp+57h+var_70], ax
0x18000ebd6  movzx   eax, word ptr cs:?g_cfURL@@3IA; uint g_cfURL
0x18000ebdd  mov     [rbp+57h+afmt.ptd], rdx
0x18000ebe1  mov     [rbp+57h+afmt.lindex], ecx
0x18000ebe4  mov     [rbp+57h+var_88], rdx
0x18000ebe8  mov     [rbp+57h+var_7C], ecx
0x18000ebeb  mov     [rbp+57h+var_68], rdx
0x18000ebef  mov     [rbp+57h+var_5C], ecx
0x18000ebf2  mov     [rbp+57h+var_48], rdx
0x18000ebf6  mov     [rbp+57h+var_3C], ecx
0x18000ebf9  mov     [rbp+57h+var_28], rdx
0x18000ebfd  lea     rdx, [rbp+57h+afmt]; afmt
0x18000ec01  mov     [rbp+57h+var_1C], ecx
0x18000ec04  lea     ecx, [r9+4]; cfmt
0x18000ec08  mov     [rbp+57h+var_50], ax
0x18000ec0c  mov     [rbp+57h+afmt.dwAspect], r9d
0x18000ec10  mov     [rbp+57h+afmt.tymed], r9d
0x18000ec14  mov     [rbp+57h+var_80], r9d
0x18000ec18  mov     [rbp+57h+var_78], 4
0x18000ec1f  mov     [rbp+57h+var_60], r9d
0x18000ec23  mov     [rbp+57h+var_58], r9d
0x18000ec27  mov     [rbp+57h+var_40], r9d
0x18000ec2b  mov     [rbp+57h+var_38], r9d
0x18000ec2f  mov     [rbp+57h+var_30], r9w
0x18000ec34  mov     [rbp+57h+var_20], r9d
0x18000ec38  mov     [rbp+57h+var_18], r9d
0x18000ec3c  call    cs:__imp_SHCreateStdEnumFmtEtc
0x18000ec42  mov     rcx, [rbp+57h+var_10]
0x18000ec46  xor     rcx, rsp; StackCookie
0x18000ec49  call    __security_check_cookie
0x18000ec4e  add     rsp, 0D0h
0x18000ec55  pop     rbp
0x18000ec56  retn
```
