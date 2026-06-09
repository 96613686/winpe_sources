# CWdsComMetadataBuilder::QueryRequiredGuid(ushort *,ushort * *)

- ea: `0x180010da0`
- end: `0x180010ff1`
- name: `?QueryRequiredGuid@CWdsComMetadataBuilder@@UEAAJPEAGPEAPEAG@Z`
- size: `593`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800085fc`
- `0x180009838`
- `0x18000b1a8`
- `0x18000e3e4`
- `0x180010da0`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010f84`
- `OLEAUT32!__imp_SysAllocString` at `0x180010f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180010fb9`
- `OLEAUT32!__imp_SysFreeString` at `0x180010fb9`

## string_xrefs

- `0x180010e44`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryRequiredGuid(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v3; // r12d
  unsigned __int8 v7; // si
  const char *v8; // rdx
  unsigned int v9; // ebx
  signed int v10; // edi
  const char *v11; // rdx
  const char *v12; // rdx
  const char *v13; // rdx
  const char *v14; // rdx
  unsigned __int16 *v15; // rdi
  __int128 v17; // [rsp+70h] [rbp-69h]
  int v18; // [rsp+80h] [rbp-59h] BYREF
  __int128 v19; // [rsp+88h] [rbp-51h]
  OLECHAR psz[8]; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v21; // [rsp+B0h] [rbp-29h]
  __int128 v22; // [rsp+C0h] [rbp-19h]
  __int128 v23; // [rsp+D0h] [rbp-9h]
  __int64 v24; // [rsp+E0h] [rbp+7h]
  int v25; // [rsp+E8h] [rbp+Fh]
  wchar_t v26; // [rsp+ECh] [rbp+13h]

  v3 = 0;
  v18 = 0;
  *(_OWORD *)psz = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v19 = 0u;
  v7 = 0;
  v22 = *(_OWORD *)L"000-0000-000000000000}";
  v21 = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v25 = *(_DWORD *)L"0}";
  v24 = *(_QWORD *)L"00000}";
  v17 = 0u;
  v23 = *(_OWORD *)L"-000000000000}";
  v26 = a00000000000000[38];
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3
    || (v9 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x892u) >= 0) )
  {
    v10 = CWdsMetadata::QueryRequired((char *)this + 64, a2, 6, &v18);
    if ( ElValidateWin32(v10, v11, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x896u)
      || ((v10 = 0, v18 != 6)
        ? (v10 = ElValidateWin32(0xDu, v12, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x6C3u))
        : (v17 = v19, v7 = BYTE8(v19), v3 = v19),
          ElValidateWin32(v10, v12, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x899u)) )
    {
      v9 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 <= 0 )
        v9 = v10;
    }
    else
    {
      v9 = StringCchPrintfW(
             psz,
             0x27u,
             L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
             v3,
             WORD2(v17),
             WORD3(v17),
             v7,
             BYTE9(v17),
             BYTE10(v17),
             BYTE11(v17),
             BYTE12(v17),
             BYTE13(v17),
             BYTE14(v17),
             HIBYTE(v17),
             v17);
      if ( (int)ElValidateHr(v9, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x89Fu) >= 0 )
      {
        v9 = 0;
        v15 = SysAllocString(psz);
        if ( !v15 )
          v9 = -2147024882;
        if ( (int)ElValidateHr(v9, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x8A2u) >= 0 )
        {
          *a3 = v15;
          v15 = 0;
        }
        if ( v15 )
          SysFreeString(v15);
      }
    }
  }
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v18);
  return v9;
}

```

## disassembly

```asm
0x180010da0  mov     [rsp-8+arg_18], rbx
0x180010da5  push    rbp
0x180010da6  push    rsi
0x180010da7  push    rdi
0x180010da8  push    r12
0x180010daa  push    r13
0x180010dac  push    r14
0x180010dae  push    r15
0x180010db0  lea     rbp, [rsp-27h]
0x180010db5  sub     rsp, 100h
0x180010dbc  mov     rax, cs:__security_cookie
0x180010dc3  xor     rax, rsp
0x180010dc6  mov     [rbp+57h+var_40], rax
0x180010dca  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180010dd1  xor     eax, eax
0x180010dd3  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180010dda  xor     r12d, r12d
0x180010ddd  and     [rbp+57h+var_B0], 0
0x180010de1  mov     r14, rcx
0x180010de4  movaps  xmmword ptr [rbp+57h+psz], xmm0
0x180010de8  mov     rcx, rdx; pbstr
0x180010deb  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180010df2  mov     r15, r8
0x180010df5  mov     qword ptr [rbp+57h+var_A8], rax
0x180010df9  mov     rdi, rdx
0x180010dfc  mov     qword ptr [rbp+57h+var_A8+8], rax
0x180010e00  mov     esi, r12d
0x180010e03  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x180010e09  movaps  [rbp+57h+var_70], xmm0
0x180010e0d  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x180010e15  movaps  [rbp+57h+var_80], xmm1
0x180010e19  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180010e20  mov     [rbp+57h+var_48], eax
0x180010e23  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x180010e2a  movsd   [rbp+57h+var_50], xmm0
0x180010e2f  mov     qword ptr [rbp+57h+var_C0], r12
0x180010e33  mov     qword ptr [rbp+57h+var_C0+8], r12
0x180010e37  movaps  [rbp+57h+var_60], xmm1
0x180010e3b  mov     [rbp+57h+var_44], ax
0x180010e3f  call    ValidateNonEmptyBstr
0x180010e44  lea     r13, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010e4b  test    eax, eax
0x180010e4d  jz      short loc_180010E54
0x180010e4f  test    r15, r15
0x180010e52  jnz     short loc_180010E71
0x180010e54  mov     ebx, 80070057h
0x180010e59  mov     r9d, 892h; unsigned int
0x180010e5f  mov     ecx, ebx; int
0x180010e61  mov     r8, r13; char *
0x180010e64  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010e69  test    eax, eax
0x180010e6b  js      loc_180010FBF
0x180010e71  lea     rcx, [r14+40h]
0x180010e75  mov     r8d, 6
0x180010e7b  lea     r9, [rbp+57h+var_B0]
0x180010e7f  mov     rdx, rdi
0x180010e82  call    ?QueryRequired@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@@Z; CWdsMetadata::QueryRequired(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *)
0x180010e87  mov     r9d, 896h; unsigned int
0x180010e8d  mov     r8, r13; char *
0x180010e90  mov     ecx, eax; unsigned int
0x180010e92  mov     edi, eax
0x180010e94  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010e99  test    eax, eax
0x180010e9b  jz      short loc_180010EB0
0x180010e9d  movzx   ebx, di
0x180010ea0  or      ebx, 80070000h
0x180010ea6  test    edi, edi
0x180010ea8  cmovle  ebx, edi
0x180010eab  jmp     loc_180010FBF
0x180010eb0  xor     edi, edi
0x180010eb2  cmp     [rbp+57h+var_B0], 6
0x180010eb6  jnz     short loc_180010ECB
0x180010eb8  movups  xmm0, [rbp+57h+var_A8]
0x180010ebc  movdqu  [rbp+57h+var_C0], xmm0
0x180010ec1  mov     rsi, qword ptr [rbp+57h+var_C0+8]
0x180010ec5  mov     r12, qword ptr [rbp+57h+var_C0]
0x180010ec9  jmp     short loc_180010EE4
0x180010ecb  mov     r9d, 6C3h; unsigned int
0x180010ed1  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x180010ed8  mov     ecx, 0Dh; unsigned int
0x180010edd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010ee2  mov     edi, eax
0x180010ee4  mov     r9d, 899h; unsigned int
0x180010eea  mov     r8, r13; char *
0x180010eed  mov     ecx, edi; unsigned int
0x180010eef  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010ef4  test    eax, eax
0x180010ef6  jnz     short loc_180010E9D
0x180010ef8  movzx   eax, byte ptr [rbp+57h+var_C0+0Fh]
0x180010efc  mov     r9d, r12d
0x180010eff  movzx   ecx, byte ptr [rbp+57h+var_C0+0Eh]
0x180010f03  movzx   edx, byte ptr [rbp+57h+var_C0+0Dh]
0x180010f07  movzx   r8d, byte ptr [rbp+57h+var_C0+0Ch]
0x180010f0c  movzx   r10d, byte ptr [rbp+57h+var_C0+0Bh]
0x180010f11  movzx   r11d, byte ptr [rbp+57h+var_C0+0Ah]
0x180010f16  movzx   ebx, byte ptr [rbp+57h+var_C0+9]
0x180010f1a  movzx   r14d, word ptr [rbp+57h+var_C0+4]
0x180010f1f  mov     [rsp+130h+var_C8], eax
0x180010f23  mov     [rsp+130h+var_D0], ecx
0x180010f27  lea     rcx, [rbp+57h+psz]; Buffer
0x180010f2b  mov     [rsp+130h+var_D8], edx
0x180010f2f  mov     edx, 27h ; '''; unsigned __int64
0x180010f34  mov     [rsp+130h+var_E0], r8d
0x180010f39  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x180010f40  mov     [rsp+130h+var_E8], r10d
0x180010f45  mov     [rsp+130h+var_F0], r11d
0x180010f4a  mov     [rsp+130h+var_F8], ebx
0x180010f4e  movzx   edi, sil
0x180010f52  movzx   esi, word ptr [rbp+57h+var_C0+6]
0x180010f56  mov     [rsp+130h+var_100], edi
0x180010f5a  mov     [rsp+130h+var_108], esi
0x180010f5e  mov     [rsp+130h+var_110], r14d
0x180010f63  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010f68  mov     r9d, 89Fh; unsigned int
0x180010f6e  mov     r8, r13; char *
0x180010f71  mov     ecx, eax; int
0x180010f73  mov     ebx, eax
0x180010f75  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010f7a  test    eax, eax
0x180010f7c  js      short loc_180010FBF
0x180010f7e  lea     rcx, [rbp+57h+psz]; psz
0x180010f82  xor     ebx, ebx
0x180010f84  call    cs:__imp_SysAllocString
0x180010f8a  mov     r9d, 8A2h; unsigned int
0x180010f90  mov     r8, r13; char *
0x180010f93  mov     rdi, rax
0x180010f96  mov     eax, 8007000Eh
0x180010f9b  test    rdi, rdi
0x180010f9e  cmovz   ebx, eax
0x180010fa1  mov     ecx, ebx; int
0x180010fa3  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010fa8  test    eax, eax
0x180010faa  js      short loc_180010FB1
0x180010fac  mov     [r15], rdi
0x180010faf  xor     edi, edi
0x180010fb1  test    rdi, rdi
0x180010fb4  jz      short loc_180010FBF
0x180010fb6  mov     rcx, rdi; bstrString
0x180010fb9  call    cs:__imp_SysFreeString
0x180010fbf  lea     rcx, [rbp+57h+var_B0]; this
0x180010fc3  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180010fc8  mov     eax, ebx
0x180010fca  mov     rcx, [rbp+57h+var_40]
0x180010fce  xor     rcx, rsp; StackCookie
0x180010fd1  call    __security_check_cookie
0x180010fd6  mov     rbx, [rsp+130h+arg_18]
0x180010fde  add     rsp, 100h
0x180010fe5  pop     r15
0x180010fe7  pop     r14
0x180010fe9  pop     r13
0x180010feb  pop     r12
0x180010fed  pop     rdi
0x180010fee  pop     rsi
0x180010fef  pop     rbp
0x180010ff0  retn
```
