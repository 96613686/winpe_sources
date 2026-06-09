# HrRegisterCOMServer(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18000ee04`
- end: `0x18000f00a`
- name: `?HrRegisterCOMServer@@YAJPEBG0000@Z`
- size: `518`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000daac`

## callees

- `0x180007820`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000abbc`
- `0x18000ac34`
- `0x18000ee04`
- `0x18000f238`
- `0x18000f484`
- `0x180012800`

## string_xrefs

- `0x18000ee2d`: `CLSID`
- `0x18000eedd`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall HrRegisterCOMServer(
        BYTE *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HKEY v6; // rcx
  int v7; // eax
  HKEY v8; // rcx
  unsigned int v9; // edi
  HKEY v10; // rcx
  _QWORD *v11; // rcx
  int v12; // edx
  PVOID *v13; // rcx
  unsigned __int16 v15[48]; // [rsp+30h] [rbp-88h] BYREF

  v15[0] = 0;
  StringCchCopyW(v15, 0x30u, L"CLSID");
  StringCchCatW(v15, 0x30u, &qword_180017630);
  StringCchCatW(v15, 0x30u, a2);
  v7 = HrSetCOMKeyAndValue(v6, v15, 0, 0, 1u, (BYTE *)L"XWizard Factory Generated Class");
  v9 = v7;
  if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_17;
    v12 = 45;
    goto LABEL_16;
  }
  v7 = HrSetCOMKeyAndValue(v8, v15, L"InprocServer32", 0, 2u, a1);
  v9 = v7;
  if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_17;
    v12 = 44;
    goto LABEL_16;
  }
  v7 = HrSetCOMKeyAndValue(v10, v15, L"InprocServer32", L"ThreadingModel", 1u, (BYTE *)L"Apartment");
  v9 = v7;
  if ( v7 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_17;
    v12 = 43;
LABEL_16:
    WPP_SF_SD(v11[2], v12, (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, (unsigned int)v15, v7);
LABEL_17:
    HrUnregisterCOMServer(a2);
    goto LABEL_18;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      (unsigned int)&WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids,
      (_DWORD)a2,
      (__int64)a1);
LABEL_18:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 )
    WPP_SF_D(v13[2], 54, &WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000ee04  mov     [rsp+arg_10], rbx
0x18000ee09  mov     [rsp+arg_18], rbp
0x18000ee0e  push    rsi
0x18000ee0f  push    rdi
0x18000ee10  push    r14
0x18000ee12  sub     rsp, 0A0h
0x18000ee19  mov     rax, cs:__security_cookie
0x18000ee20  xor     rax, rsp
0x18000ee23  mov     [rsp+0B8h+var_28], rax
0x18000ee2b  xor     eax, eax
0x18000ee2d  lea     r8, aClsid_0; "CLSID"
0x18000ee34  mov     rbp, rdx
0x18000ee37  mov     [rsp+0B8h+var_88], ax
0x18000ee3c  mov     rsi, rcx
0x18000ee3f  lea     rcx, [rsp+0B8h+var_88]; unsigned __int16 *
0x18000ee44  lea     ebx, [rax+30h]
0x18000ee47  mov     edx, ebx; unsigned __int64
0x18000ee49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ee4e  lea     r8, qword_180017630; unsigned __int16 *
0x18000ee55  mov     edx, ebx; unsigned __int64
0x18000ee57  lea     rcx, [rsp+0B8h+var_88]; unsigned __int16 *
0x18000ee5c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee61  mov     r8, rbp; unsigned __int16 *
0x18000ee64  lea     rcx, [rsp+0B8h+var_88]; unsigned __int16 *
0x18000ee69  mov     edx, ebx; unsigned __int64
0x18000ee6b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee70  lea     rax, aXwizardFactory; "XWizard Factory Generated Class"
0x18000ee77  mov     ebx, 1
0x18000ee7c  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x18000ee81  lea     rdx, [rsp+0B8h+var_88]; unsigned __int16 *
0x18000ee86  xor     r9d, r9d; unsigned __int16 *
0x18000ee89  mov     [rsp+0B8h+var_98], ebx; unsigned int
0x18000ee8d  xor     r8d, r8d; unsigned __int16 *
0x18000ee90  call    ?HrSetCOMKeyAndValue@@YAJQEAUHKEY__@@PEBG11K1@Z; HrSetCOMKeyAndValue(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong,ushort const *)
0x18000ee95  lea     r14, WPP_aa8c428c8bc735eb8d68746a0a76c954_Traceguids
0x18000ee9c  mov     edi, eax
0x18000ee9e  test    eax, eax
0x18000eea0  js      loc_18000EF7F
0x18000eea6  mov     [rsp+0B8h+var_90], rsi; unsigned __int16 *
0x18000eeab  lea     r8, aInprocserver32; "InprocServer32"
0x18000eeb2  xor     r9d, r9d; unsigned __int16 *
0x18000eeb5  mov     [rsp+0B8h+var_98], 2; unsigned int
0x18000eebd  lea     rdx, [rsp+0B8h+var_88]; unsigned __int16 *
0x18000eec2  call    ?HrSetCOMKeyAndValue@@YAJQEAUHKEY__@@PEBG11K1@Z; HrSetCOMKeyAndValue(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong,ushort const *)
0x18000eec7  mov     edi, eax
0x18000eec9  test    eax, eax
0x18000eecb  js      loc_18000EF5F
0x18000eed1  lea     rax, aApartment; "Apartment"
0x18000eed8  mov     [rsp+0B8h+var_90], rax; unsigned __int16 *
0x18000eedd  lea     r9, aThreadingmodel; "ThreadingModel"
0x18000eee4  lea     r8, aInprocserver32; "InprocServer32"
0x18000eeeb  mov     [rsp+0B8h+var_98], ebx; unsigned int
0x18000eeef  lea     rdx, [rsp+0B8h+var_88]; unsigned __int16 *
0x18000eef4  call    ?HrSetCOMKeyAndValue@@YAJQEAUHKEY__@@PEBG11K1@Z; HrSetCOMKeyAndValue(HKEY__ * const,ushort const *,ushort const *,ushort const *,ulong,ushort const *)
0x18000eef9  mov     edi, eax
0x18000eefb  test    eax, eax
0x18000eefd  jns     short loc_18000EF27
0x18000eeff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef06  lea     rbx, WPP_GLOBAL_Control
0x18000ef0d  cmp     rcx, rbx
0x18000ef10  jz      loc_18000EFB2
0x18000ef16  test    byte ptr [rcx+1Ch], 4
0x18000ef1a  jz      loc_18000EFB2
0x18000ef20  mov     edx, 2Bh ; '+'
0x18000ef25  jmp     short loc_18000EF9D
0x18000ef27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef2e  lea     rbx, WPP_GLOBAL_Control
0x18000ef35  cmp     rcx, rbx
0x18000ef38  jz      loc_18000EFE0
0x18000ef3e  test    byte ptr [rcx+1Ch], 8
0x18000ef42  jz      short loc_18000EFC1
0x18000ef44  mov     rcx, [rcx+10h]
0x18000ef48  mov     edx, 35h ; '5'
0x18000ef4d  mov     r9, rbp
0x18000ef50  mov     qword ptr [rsp+0B8h+var_98], rsi
0x18000ef55  mov     r8, r14
0x18000ef58  call    WPP_SF_SS
0x18000ef5d  jmp     short loc_18000EFBA
0x18000ef5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef66  lea     rbx, WPP_GLOBAL_Control
0x18000ef6d  cmp     rcx, rbx
0x18000ef70  jz      short loc_18000EFB2
0x18000ef72  test    byte ptr [rcx+1Ch], 4
0x18000ef76  jz      short loc_18000EFB2
0x18000ef78  mov     edx, 2Ch ; ','
0x18000ef7d  jmp     short loc_18000EF9D
0x18000ef7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef86  lea     rbx, WPP_GLOBAL_Control
0x18000ef8d  cmp     rcx, rbx
0x18000ef90  jz      short loc_18000EFB2
0x18000ef92  test    byte ptr [rcx+1Ch], 4
0x18000ef96  jz      short loc_18000EFB2
0x18000ef98  mov     edx, 2Dh ; '-'
0x18000ef9d  mov     rcx, [rcx+10h]
0x18000efa1  lea     r9, [rsp+0B8h+var_88]
0x18000efa6  mov     r8, r14
0x18000efa9  mov     [rsp+0B8h+var_98], eax
0x18000efad  call    WPP_SF_SD
0x18000efb2  mov     rcx, rbp; unsigned __int16 *
0x18000efb5  call    ?HrUnregisterCOMServer@@YAJPEBG@Z; HrUnregisterCOMServer(ushort const *)
0x18000efba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efc1  cmp     rcx, rbx
0x18000efc4  jz      short loc_18000EFE0
0x18000efc6  test    byte ptr [rcx+1Ch], 10h
0x18000efca  jz      short loc_18000EFE0
0x18000efcc  mov     rcx, [rcx+10h]
0x18000efd0  mov     edx, 36h ; '6'
0x18000efd5  mov     r9d, edi
0x18000efd8  mov     r8, r14
0x18000efdb  call    WPP_SF_D
0x18000efe0  mov     eax, edi
0x18000efe2  mov     rcx, [rsp+0B8h+var_28]
0x18000efea  xor     rcx, rsp; StackCookie
0x18000efed  call    __security_check_cookie
0x18000eff2  lea     r11, [rsp+0B8h+var_18]
0x18000effa  mov     rbx, [r11+30h]
0x18000effe  mov     rbp, [r11+38h]
0x18000f002  mov     rsp, r11
0x18000f005  pop     r14
0x18000f007  pop     rdi
0x18000f008  pop     rsi
0x18000f009  retn
```
