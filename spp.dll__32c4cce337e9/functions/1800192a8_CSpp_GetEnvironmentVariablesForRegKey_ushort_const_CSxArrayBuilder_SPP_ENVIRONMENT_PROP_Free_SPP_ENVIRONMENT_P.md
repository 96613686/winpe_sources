# CSpp::_GetEnvironmentVariablesForRegKey(ushort const *,CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)> *)

- ea: `0x1800192a8`
- end: `0x18001951c`
- name: `?_GetEnvironmentVariablesForRegKey@CSpp@@AEAAJPEBGPEAV?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180018f10`

## callees

- `0x180003b24`
- `0x1800192a8`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002be5c`
- `0x18002dff4`
- `0x180034804`
- `0x180035b00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800194e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019393`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019393`

## pseudocode

```c
__int64 __fastcall CSpp::_GetEnvironmentVariablesForRegKey(__int64 a1, const WCHAR *a2, __int64 a3)
{
  __int16 v5; // ax
  LSTATUS v6; // eax
  signed int v7; // ebx
  int v8; // eax
  __int64 v9; // r8
  char *v10; // rdx
  unsigned __int16 *v12[2]; // [rsp+38h] [rbp-39h] BYREF
  unsigned __int16 *v13[2]; // [rsp+48h] [rbp-29h] BYREF
  unsigned __int16 *Src[2]; // [rsp+58h] [rbp-19h] BYREF
  int v15; // [rsp+68h] [rbp-9h] BYREF
  __int16 v16; // [rsp+6Ch] [rbp-5h]
  __int16 v17; // [rsp+6Eh] [rbp-3h]
  __int64 v18; // [rsp+D8h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp+6Fh] BYREF

  v18 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CSpp::_GetEnvironmentVariablesForRegKey", 4232, 1);
  hKey = 0;
  Src[0] = (unsigned __int16 *)&FileName;
  v13[0] = (unsigned __int16 *)&FileName;
  v5 = 4239;
  LODWORD(v18) = 0;
  Src[1] = 0;
  v13[1] = 0;
  if ( a2 && (v16 = 4239, v5 = 4240, a3) )
  {
    v16 = 4240;
    v15 = 0;
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    v15 = v7;
    if ( v7 >= 0 )
    {
      v16 = 4242;
      while ( !v7 )
      {
        v8 = SxRegEnumString(hKey, (unsigned int *)&v18, (struct CBsString *)Src, (struct CBsString *)v13);
        v15 = v8;
        v7 = v8;
        if ( v8 < 0 )
        {
          v17 = 4246;
          goto LABEL_23;
        }
        v16 = 4246;
        if ( !v8 )
        {
          *(_OWORD *)v12 = 0;
          v15 = SxCopyString(Src[0], v12);
          v7 = v15;
          if ( v15 < 0 )
          {
            v17 = 4251;
            goto LABEL_23;
          }
          v16 = 4251;
          v15 = SxCopyString(v13[0], &v12[1]);
          v7 = v15;
          if ( v15 < 0 )
          {
            v17 = 4252;
            goto LABEL_23;
          }
          v16 = 4252;
          v15 = CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&void Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&void SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&void SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(
                  a3,
                  v12);
          v7 = v15;
          if ( v15 < 0 )
          {
            v17 = 4254;
            goto LABEL_23;
          }
          v16 = 4254;
          Free_SPP_ENVIRONMENT_PROP((struct _SPP_ENVIRONMENT_PROP *)v12);
          LODWORD(v18) = v18 + 1;
          v7 = v15;
        }
      }
      v7 = 0;
      v15 = 0;
      v16 = 4261;
    }
    else
    {
      v17 = 4242;
    }
LABEL_23:
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      v7 = v15;
      hKey = 0;
    }
  }
  else
  {
    v7 = -2147024809;
    v17 = v5;
    v15 = -2147024809;
  }
  CBsString::_Release((CBsString *)v13);
  CBsString::_Release((CBsString *)Src);
  v10 = (char *)hKey - 1;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15, (__int64)v10, v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800192a8  mov     rax, rsp
0x1800192ab  mov     [rax+18h], rbx
0x1800192af  mov     [rax+20h], rdi
0x1800192b3  mov     [rax+8], rcx
0x1800192b7  push    rbp
0x1800192b8  push    r12
0x1800192ba  push    r13
0x1800192bc  push    r14
0x1800192be  push    r15
0x1800192c0  lea     rbp, [rax-5Fh]
0x1800192c4  sub     rsp, 0A0h
0x1800192cb  mov     rdi, r8
0x1800192ce  mov     rbx, rdx
0x1800192d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192d8  lea     rax, WPP_GLOBAL_Control
0x1800192df  cmp     rcx, rax
0x1800192e2  jz      short loc_180019302
0x1800192e4  test    dword ptr [rcx+1Ch], 20000000h
0x1800192eb  jz      short loc_180019302
0x1800192ed  mov     rcx, [rcx+10h]
0x1800192f1  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800192f8  mov     edx, 36h ; '6'
0x1800192fd  call    WPP_SF_
0x180019302  mov     r9d, 1; unsigned __int16
0x180019308  lea     rdx, aCsppGetenviron_0; "CSpp::_GetEnvironmentVariablesForRegKey"
0x18001930f  mov     r8d, 1088h; unsigned __int16
0x180019315  lea     rcx, [rbp+57h+var_60]; this
0x180019319  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001931e  mov     [rbp+57h+hKey], 0
0x180019326  lea     rax, FileName
0x18001932d  mov     [rbp+57h+Src], rax
0x180019331  mov     [rbp+57h+var_80], rax
0x180019335  mov     eax, 108Fh
0x18001933a  mov     dword ptr [rbp+57h+arg_0], 0
0x180019341  mov     [rbp+57h+var_68], 0
0x180019349  mov     [rbp+57h+var_78], 0
0x180019351  test    rbx, rbx
0x180019354  jz      loc_1800194BA
0x18001935a  mov     [rbp+57h+var_5C], ax
0x18001935e  mov     eax, 1090h
0x180019363  test    rdi, rdi
0x180019366  jz      loc_1800194BA
0x18001936c  mov     [rbp+57h+var_5C], ax
0x180019370  mov     r9d, 20019h; samDesired
0x180019376  lea     rax, [rbp+57h+hKey]
0x18001937a  mov     [rbp+57h+var_60], 0
0x180019381  xor     r8d, r8d; ulOptions
0x180019384  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180019389  mov     rdx, rbx; lpSubKey
0x18001938c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019393  call    cs:__imp_RegOpenKeyExW
0x180019399  mov     ebx, eax
0x18001939b  test    eax, eax
0x18001939d  jle     short loc_1800193A8
0x18001939f  movzx   ebx, ax
0x1800193a2  or      ebx, 80070000h
0x1800193a8  mov     [rbp+57h+var_60], ebx
0x1800193ab  mov     eax, 1092h
0x1800193b0  test    ebx, ebx
0x1800193b2  jns     short loc_1800193BD
0x1800193b4  mov     [rbp+57h+var_5A], ax
0x1800193b8  jmp     loc_180019499
0x1800193bd  mov     r15d, 1096h
0x1800193c3  mov     [rbp+57h+var_5C], ax
0x1800193c7  lea     r13d, [r15+5]
0x1800193cb  lea     r12d, [r15+6]
0x1800193cf  lea     r14d, [r15+8]
0x1800193d3  test    ebx, ebx
0x1800193d5  jnz     loc_18001948B
0x1800193db  mov     rcx, [rbp+57h+hKey]; hKey
0x1800193df  lea     r9, [rbp+57h+var_80]; struct CBsString *
0x1800193e3  lea     r8, [rbp+57h+Src]; struct CBsString *
0x1800193e7  lea     rdx, [rbp+57h+arg_0]; unsigned int *
0x1800193eb  call    ?SxRegEnumString@@YAJPEAUHKEY__@@PEAKPEAVCBsString@@2@Z; SxRegEnumString(HKEY__ *,ulong *,CBsString *,CBsString *)
0x1800193f0  mov     [rbp+57h+var_60], eax
0x1800193f3  mov     ebx, eax
0x1800193f5  test    eax, eax
0x1800193f7  js      loc_180019484
0x1800193fd  mov     [rbp+57h+var_5C], r15w
0x180019402  jnz     short loc_1800193D3
0x180019404  mov     rcx, [rbp+57h+Src]; Src
0x180019408  lea     rdx, [rbp+57h+var_90]; unsigned __int16 **
0x18001940c  xorps   xmm0, xmm0
0x18001940f  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x180019413  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180019418  mov     [rbp+57h+var_60], eax
0x18001941b  mov     ebx, eax
0x18001941d  test    eax, eax
0x18001941f  js      short loc_18001947D
0x180019421  mov     rcx, [rbp+57h+var_80]; Src
0x180019425  lea     rdx, [rbp+57h+var_90+8]; unsigned __int16 **
0x180019429  mov     [rbp+57h+var_5C], r13w
0x18001942e  call    ?SxCopyString@@YAJPEBGPEAPEAG@Z; SxCopyString(ushort const *,ushort * *)
0x180019433  mov     [rbp+57h+var_60], eax
0x180019436  mov     ebx, eax
0x180019438  test    eax, eax
0x18001943a  js      short loc_180019476
0x18001943c  lea     rdx, [rbp+57h+var_90]
0x180019440  mov     [rbp+57h+var_5C], r12w
0x180019445  mov     rcx, rdi
0x180019448  call    ?Append@?$CSxArrayBuilder@U_SPP_ENVIRONMENT_PROP@@$1?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU1@@Z$1??$SxDefaultInit@U_SPP_ENVIRONMENT_PROP@@@@YAX0@Z$1??$SxDefaultTransfer@U_SPP_ENVIRONMENT_PROP@@@@YAX00@Z@@QEAAJPEAU_SPP_ENVIRONMENT_PROP@@@Z; CSxArrayBuilder<_SPP_ENVIRONMENT_PROP,&Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *),&SxDefaultInit<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *),&SxDefaultTransfer<_SPP_ENVIRONMENT_PROP>(_SPP_ENVIRONMENT_PROP *,_SPP_ENVIRONMENT_PROP *)>::Append(_SPP_ENVIRONMENT_PROP *)
0x18001944d  mov     [rbp+57h+var_60], eax
0x180019450  mov     ebx, eax
0x180019452  test    eax, eax
0x180019454  js      short loc_18001946F
0x180019456  lea     rcx, [rbp+57h+var_90]; struct _SPP_ENVIRONMENT_PROP *
0x18001945a  mov     [rbp+57h+var_5C], r14w
0x18001945f  call    ?Free_SPP_ENVIRONMENT_PROP@@YAXPEAU_SPP_ENVIRONMENT_PROP@@@Z; Free_SPP_ENVIRONMENT_PROP(_SPP_ENVIRONMENT_PROP *)
0x180019464  inc     dword ptr [rbp+57h+arg_0]
0x180019467  mov     ebx, [rbp+57h+var_60]
0x18001946a  jmp     loc_1800193D3
0x18001946f  mov     [rbp+57h+var_5A], r14w
0x180019474  jmp     short loc_180019499
0x180019476  mov     [rbp+57h+var_5A], r12w
0x18001947b  jmp     short loc_180019499
0x18001947d  mov     [rbp+57h+var_5A], r13w
0x180019482  jmp     short loc_180019499
0x180019484  mov     [rbp+57h+var_5A], r15w
0x180019489  jmp     short loc_180019499
0x18001948b  xor     ebx, ebx
0x18001948d  mov     eax, 10A5h
0x180019492  mov     [rbp+57h+var_60], ebx
0x180019495  mov     [rbp+57h+var_5C], ax
0x180019499  mov     rcx, [rbp+57h+hKey]; hKey
0x18001949d  lea     rax, [rcx-1]
0x1800194a1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800194a5  ja      short loc_1800194C6
0x1800194a7  call    cs:__imp_RegCloseKey
0x1800194ad  mov     ebx, [rbp+57h+var_60]
0x1800194b0  mov     [rbp+57h+hKey], 0
0x1800194b8  jmp     short loc_1800194C6
0x1800194ba  mov     ebx, 80070057h
0x1800194bf  mov     [rbp+57h+var_5A], ax
0x1800194c3  mov     [rbp+57h+var_60], ebx
0x1800194c6  lea     rcx, [rbp+57h+var_80]; this
0x1800194ca  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800194cf  lea     rcx, [rbp+57h+Src]; this
0x1800194d3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x1800194d8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800194dc  lea     rdx, [rcx-1]
0x1800194e0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800194e4  ja      short loc_1800194F4
0x1800194e6  call    cs:__imp_RegCloseKey
0x1800194ec  mov     [rbp+57h+hKey], 0
0x1800194f4  lea     rcx, [rbp+57h+var_60]; this
0x1800194f8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800194fd  lea     r11, [rsp+0C0h+var_20]
0x180019505  mov     eax, ebx
0x180019507  mov     rbx, [r11+40h]
0x18001950b  mov     rdi, [r11+48h]
0x18001950f  mov     rsp, r11
0x180019512  pop     r15
0x180019514  pop     r14
0x180019516  pop     r13
0x180019518  pop     r12
0x18001951a  pop     rbp
0x18001951b  retn
```
