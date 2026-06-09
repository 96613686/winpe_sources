# CWdsComMetadataBuilder::QueryOptionalGuid(ushort *,ushort *,short *,ushort * *)

- ea: `0x1800102e0`
- end: `0x1800105c3`
- name: `?QueryOptionalGuid@CWdsComMetadataBuilder@@UEAAJPEAG0PEAFPEAPEAG@Z`
- size: `739`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int16 *, __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800085fc`
- `0x180009838`
- `0x18000af78`
- `0x18000e3e4`
- `0x1800102e0`
- `0x180014010`
- `0x180014d58`
- `0x180014ee0`
- `0x180015660`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180010540`
- `OLEAUT32!__imp_SysAllocString` at `0x180010540`
- `OLEAUT32!__imp_SysFreeString` at `0x180010589`
- `OLEAUT32!__imp_SysFreeString` at `0x180010589`

## string_xrefs

- `0x1800103b7`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x1800103e5`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010431`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18001048e`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x180010526`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18001054c`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::QueryOptionalGuid(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int16 *a4,
        unsigned __int16 **a5)
{
  int v9; // r14d
  const char *v10; // rdx
  unsigned int v11; // ebx
  signed int v12; // edi
  const char *v13; // rdx
  const char *v14; // rdx
  const char *v15; // rdx
  const char *v16; // rdx
  const char *v17; // rdx
  unsigned __int16 *v18; // rdi
  __int64 v20; // [rsp+20h] [rbp-E0h]
  struct _GUID v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v23; // [rsp+88h] [rbp-78h]
  struct _GUID v24; // [rsp+A0h] [rbp-60h] BYREF
  int v25; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+B8h] [rbp-48h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  OLECHAR psz[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v29; // [rsp+E0h] [rbp-20h]
  __int128 v30; // [rsp+F0h] [rbp-10h]
  __int128 v31; // [rsp+100h] [rbp+0h]
  __int64 v32; // [rsp+110h] [rbp+10h]
  int v33; // [rsp+118h] [rbp+18h]
  wchar_t v34; // [rsp+11Ch] [rbp+1Ch]

  v22 = 0;
  v25 = 0;
  *(_OWORD *)psz = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v9 = 0;
  v26 = 0;
  v27 = 0;
  v23 = (struct _GUID)0LL;
  v21 = (struct _GUID)0LL;
  *(_QWORD *)&v24.Data1 = 0;
  *(_QWORD *)v24.Data4 = 0;
  v30 = *(_OWORD *)L"000-0000-000000000000}";
  v29 = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v33 = *(_DWORD *)L"0}";
  v32 = *(_QWORD *)L"00000}";
  v31 = *(_OWORD *)L"-000000000000}";
  v34 = a00000000000000[38];
  if ( !(unsigned int)ValidateNonEmptyBstr(a2) || !(unsigned int)ValidateNonEmptyBstr(a3) || !a5 )
  {
    v11 = -2147024809;
    if ( (int)ElValidateHr(-2147024809, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x6D5u) < 0 )
      goto LABEL_24;
  }
  v12 = ParseGuid(a3, &v24);
  if ( ElValidateWin32(v12, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x6D9u) )
    goto LABEL_6;
  v12 = CWdsMetadata::QueryOptional((char *)this + 64, a2, 6, &v22, &v25);
  if ( ElValidateWin32(v12, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x6DCu) )
    goto LABEL_6;
  if ( !v22 )
  {
    v9 = 1;
    v21 = v24;
    goto LABEL_16;
  }
  v12 = 0;
  if ( v22 == 6 )
    v21 = v23;
  else
    v12 = ElValidateWin32(0xDu, v15, "base\\eco\\wds\\lib\\metadata\\core\\metadata.cpp", 0x6C3u);
  if ( ElValidateWin32(v12, v15, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x6E6u) )
  {
LABEL_6:
    v11 = (unsigned __int16)v12 | 0x80070000;
    if ( v12 <= 0 )
      v11 = v12;
    goto LABEL_24;
  }
LABEL_16:
  LODWORD(v20) = v21.Data2;
  v11 = StringCchPrintfW(
          psz,
          0x27u,
          L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
          v21.Data1,
          v20,
          v21.Data3,
          v21.Data4[0],
          v21.Data4[1],
          v21.Data4[2],
          v21.Data4[3],
          v21.Data4[4],
          v21.Data4[5],
          v21.Data4[6],
          v21.Data4[7]);
  if ( (int)ElValidateHr(v11, v16, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x6F1u) >= 0 )
  {
    v11 = 0;
    v18 = SysAllocString(psz);
    if ( !v18 )
      v11 = -2147024882;
    if ( (int)ElValidateHr(v11, v17, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x6F4u) >= 0 )
    {
      *a5 = v18;
      v18 = 0;
      if ( !a4 )
        goto LABEL_24;
      *a4 = -(v9 != 0);
    }
    if ( v18 )
      SysFreeString(v18);
  }
LABEL_24:
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v22);
  CWdsMetadataValue::Shutdown((CWdsMetadataValue *)&v25);
  return v11;
}

```

## disassembly

```asm
0x1800102e0  push    rbp
0x1800102e2  push    rbx
0x1800102e3  push    rsi
0x1800102e4  push    rdi
0x1800102e5  push    r12
0x1800102e7  push    r13
0x1800102e9  push    r14
0x1800102eb  push    r15
0x1800102ed  lea     rbp, [rsp-38h]
0x1800102f2  sub     rsp, 138h
0x1800102f9  mov     rax, cs:__security_cookie
0x180010300  xor     rax, rsp
0x180010303  mov     [rbp+70h+var_50], rax
0x180010307  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18001030e  xor     eax, eax
0x180010310  and     [rbp+70h+var_F0], eax
0x180010313  mov     r13, rcx
0x180010316  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18001031d  mov     rcx, rdx; pbstr
0x180010320  mov     r12, [rbp+70h+arg_20]
0x180010327  mov     r15, r9
0x18001032a  and     [rbp+70h+var_C0], 0
0x18001032e  mov     rdi, r8
0x180010331  movaps  xmmword ptr [rbp+70h+psz], xmm0
0x180010335  mov     rsi, rdx
0x180010338  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18001033f  xor     r14d, r14d
0x180010342  mov     [rbp+70h+var_B8], rax
0x180010346  mov     [rbp+70h+var_B0], rax
0x18001034a  mov     qword ptr [rbp+70h+var_E8], rax
0x18001034e  mov     qword ptr [rbp+70h+var_E8+8], rax
0x180010352  mov     qword ptr [rsp+170h+var_100], rax
0x180010357  mov     qword ptr [rsp+170h+var_100+8], rax
0x18001035c  mov     qword ptr [rbp+70h+var_D0.Data1], rax
0x180010360  mov     qword ptr [rbp+70h+var_D0.Data4], rax
0x180010364  mov     eax, dword ptr cs:a00000000000000+48h; "0}"
0x18001036a  movaps  [rbp+70h+var_80], xmm0
0x18001036e  movsd   xmm0, qword ptr cs:a00000000000000+40h; "00000}"
0x180010376  movaps  [rbp+70h+var_90], xmm1
0x18001037a  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180010381  mov     [rbp+70h+var_58], eax
0x180010384  movzx   eax, word ptr cs:a00000000000000+4Ch; ""
0x18001038b  movsd   [rbp+70h+var_60], xmm0
0x180010390  movaps  [rbp+70h+var_70], xmm1
0x180010394  mov     [rbp+70h+var_54], ax
0x180010398  call    ValidateNonEmptyBstr
0x18001039d  test    eax, eax
0x18001039f  jz      short loc_1800103B2
0x1800103a1  mov     rcx, rdi; pbstr
0x1800103a4  call    ValidateNonEmptyBstr
0x1800103a9  test    eax, eax
0x1800103ab  jz      short loc_1800103B2
0x1800103ad  test    r12, r12
0x1800103b0  jnz     short loc_1800103D3
0x1800103b2  mov     ebx, 80070057h
0x1800103b7  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800103be  mov     ecx, ebx; int
0x1800103c0  mov     r9d, 6D5h; unsigned int
0x1800103c6  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x1800103cb  test    eax, eax
0x1800103cd  js      loc_18001058F
0x1800103d3  lea     rdx, [rbp+70h+var_D0]; struct _GUID *
0x1800103d7  mov     rcx, rdi; String
0x1800103da  call    ?ParseGuid@@YAKPEBGPEAU_GUID@@@Z; ParseGuid(ushort const *,_GUID *)
0x1800103df  mov     r9d, 6D9h; unsigned int
0x1800103e5  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x1800103ec  mov     ecx, eax; unsigned int
0x1800103ee  mov     edi, eax
0x1800103f0  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x1800103f5  test    eax, eax
0x1800103f7  jz      short loc_18001040C
0x1800103f9  movzx   ebx, di
0x1800103fc  or      ebx, 80070000h
0x180010402  test    edi, edi
0x180010404  cmovle  ebx, edi
0x180010407  jmp     loc_18001058F
0x18001040c  lea     rax, [rbp+70h+var_C0]
0x180010410  mov     r8d, 6
0x180010416  lea     rcx, [r13+40h]
0x18001041a  mov     [rsp+170h+var_150], rax
0x18001041f  lea     r9, [rbp+70h+var_F0]
0x180010423  mov     rdx, rsi
0x180010426  call    ?QueryOptional@CWdsMetadata@@QEBAKPEBGW4WDS_METADATA_VALUE_TYPE@@PEAVCWdsMetadataValue@@PEBV3@@Z; CWdsMetadata::QueryOptional(ushort const *,WDS_METADATA_VALUE_TYPE,CWdsMetadataValue *,CWdsMetadataValue const *)
0x18001042b  mov     r9d, 6DCh; unsigned int
0x180010431  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010438  mov     ecx, eax; unsigned int
0x18001043a  mov     edi, eax
0x18001043c  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010441  test    eax, eax
0x180010443  jnz     short loc_1800103F9
0x180010445  mov     eax, [rbp+70h+var_F0]
0x180010448  test    eax, eax
0x18001044a  jnz     short loc_18001045C
0x18001044c  movaps  xmm0, xmmword ptr [rbp+70h+var_D0.Data1]
0x180010450  lea     r14d, [rax+1]
0x180010454  movdqa  [rsp+170h+var_100], xmm0
0x18001045a  jmp     short loc_1800104A4
0x18001045c  xor     edi, edi
0x18001045e  cmp     eax, 6
0x180010461  jnz     short loc_18001046F
0x180010463  movups  xmm0, [rbp+70h+var_E8]
0x180010467  movdqu  [rsp+170h+var_100], xmm0
0x18001046d  jmp     short loc_180010488
0x18001046f  mov     r9d, 6C3h; unsigned int
0x180010475  lea     r8, aBaseEcoWdsLibM; "base\\eco\\wds\\lib\\metadata\\core\\me"...
0x18001047c  mov     ecx, 0Dh; unsigned int
0x180010481  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180010486  mov     edi, eax
0x180010488  mov     r9d, 6E6h; unsigned int
0x18001048e  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010495  mov     ecx, edi; unsigned int
0x180010497  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001049c  test    eax, eax
0x18001049e  jnz     loc_1800103F9
0x1800104a4  movzx   r9d, byte ptr [rsp+170h+var_100+0Bh]
0x1800104aa  movzx   eax, byte ptr [rsp+170h+var_100+0Fh]
0x1800104af  movzx   ecx, byte ptr [rsp+170h+var_100+0Eh]
0x1800104b4  movzx   edx, byte ptr [rsp+170h+var_100+0Dh]
0x1800104b9  movzx   r8d, byte ptr [rsp+170h+var_100+0Ch]
0x1800104bf  movzx   r10d, byte ptr [rsp+170h+var_100+0Ah]
0x1800104c5  movzx   r11d, byte ptr [rsp+170h+var_100+9]
0x1800104cb  movzx   ebx, byte ptr [rsp+170h+var_100+8]
0x1800104d0  movzx   edi, word ptr [rsp+170h+var_100+6]
0x1800104d5  movzx   esi, word ptr [rsp+170h+var_100+4]
0x1800104da  mov     [rsp+170h+var_108], eax
0x1800104de  mov     [rsp+170h+var_110], ecx
0x1800104e2  lea     rcx, [rbp+70h+psz]; Buffer
0x1800104e6  mov     [rsp+170h+var_118], edx
0x1800104ea  mov     edx, 27h ; '''; unsigned __int64
0x1800104ef  mov     [rsp+170h+var_120], r8d
0x1800104f4  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x1800104fb  mov     [rsp+170h+var_128], r9d
0x180010500  mov     r9d, dword ptr [rsp+170h+var_100]
0x180010505  mov     [rsp+170h+var_130], r10d
0x18001050a  mov     [rsp+170h+var_138], r11d
0x18001050f  mov     [rsp+170h+var_140], ebx
0x180010513  mov     [rsp+170h+var_148], edi
0x180010517  mov     dword ptr [rsp+170h+var_150], esi
0x18001051b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010520  mov     r9d, 6F1h; unsigned int
0x180010526  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18001052d  mov     ecx, eax; int
0x18001052f  mov     ebx, eax
0x180010531  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010536  test    eax, eax
0x180010538  js      short loc_18001058F
0x18001053a  lea     rcx, [rbp+70h+psz]; psz
0x18001053e  xor     ebx, ebx
0x180010540  call    cs:__imp_SysAllocString
0x180010546  mov     r9d, 6F4h; unsigned int
0x18001054c  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x180010553  mov     rdi, rax
0x180010556  mov     eax, 8007000Eh
0x18001055b  test    rdi, rdi
0x18001055e  cmovz   ebx, eax
0x180010561  mov     ecx, ebx; int
0x180010563  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180010568  test    eax, eax
0x18001056a  js      short loc_180010581
0x18001056c  mov     [r12], rdi
0x180010570  xor     edi, edi
0x180010572  test    r15, r15
0x180010575  jz      short loc_18001058F
0x180010577  neg     r14d
0x18001057a  sbb     ax, ax
0x18001057d  mov     [r15], ax
0x180010581  test    rdi, rdi
0x180010584  jz      short loc_18001058F
0x180010586  mov     rcx, rdi; bstrString
0x180010589  call    cs:__imp_SysFreeString
0x18001058f  lea     rcx, [rbp+70h+var_F0]; this
0x180010593  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x180010598  lea     rcx, [rbp+70h+var_C0]; this
0x18001059c  call    ?Shutdown@CWdsMetadataValue@@QEAAXXZ; CWdsMetadataValue::Shutdown(void)
0x1800105a1  mov     eax, ebx
0x1800105a3  mov     rcx, [rbp+70h+var_50]
0x1800105a7  xor     rcx, rsp; StackCookie
0x1800105aa  call    __security_check_cookie
0x1800105af  add     rsp, 138h
0x1800105b6  pop     r15
0x1800105b8  pop     r14
0x1800105ba  pop     r13
0x1800105bc  pop     r12
0x1800105be  pop     rdi
0x1800105bf  pop     rsi
0x1800105c0  pop     rbx
0x1800105c1  pop     rbp
0x1800105c2  retn
```
