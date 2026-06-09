# CSpp::_CreateRegKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x1800141ac`
- end: `0x180014313`
- name: `?_CreateRegKey@CSpp@@AEAAJPEAUHKEY__@@PEBGPEAPEAU2@@Z`
- size: `359`
- prototype: `__int64 __fastcall(CSpp *this, HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a430`
- `0x18000e7b0`
- `0x180019a04`
- `0x18001f31c`

## callees

- `0x1800141ac`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800142df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800142df`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001429e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001429e`

## string_xrefs

- `0x180014209`: `CSpp::_CreateRegKey`

## pseudocode

```c
__int64 __fastcall CSpp::_CreateRegKey(CSpp *this, HKEY a2, const unsigned __int16 *a3, HKEY *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int16 v10; // ax
  signed int v11; // ebx
  LSTATUS v12; // eax
  HKEY v13; // rcx
  int v15; // [rsp+50h] [rbp+7h] BYREF
  __int16 v16; // [rsp+54h] [rbp+Bh]
  __int16 v17; // [rsp+56h] [rbp+Dh]
  HKEY phkResult; // [rsp+C0h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "CSpp::_CreateRegKey", 2164, 1);
  phkResult = 0;
  if ( a4 )
    *a4 = 0;
  v10 = 2171;
  if ( a3 && (v16 = 2171, v10 = 2172, a4) )
  {
    v16 = 2172;
    v15 = 0;
    v12 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0x2001Fu, (const LPSECURITY_ATTRIBUTES)((char *)this + 56), &phkResult, 0);
    v11 = v12;
    if ( v12 > 0 )
      v11 = (unsigned __int16)v12 | 0x80070000;
    v15 = v11;
    if ( v11 >= 0 )
    {
      v16 = 2183;
      v13 = 0;
      *a4 = phkResult;
      phkResult = 0;
    }
    else
    {
      v13 = phkResult;
      v17 = 2183;
    }
    if ( v13 )
    {
      RegCloseKey(v13);
      v11 = v15;
      phkResult = 0;
    }
  }
  else
  {
    v11 = -2147024809;
    v17 = v10;
    v15 = -2147024809;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15, v8, v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800141ac  mov     [rsp-8+arg_0], rbx
0x1800141b1  mov     [rsp-8+arg_8], rsi
0x1800141b6  push    rbp
0x1800141b7  push    rdi
0x1800141b8  push    r14
0x1800141ba  lea     rbp, [rsp-47h]
0x1800141bf  sub     rsp, 90h
0x1800141c6  mov     rdi, r9
0x1800141c9  mov     rbx, r8
0x1800141cc  mov     rsi, rdx
0x1800141cf  mov     r14, rcx
0x1800141d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141d9  lea     rax, WPP_GLOBAL_Control
0x1800141e0  cmp     rcx, rax
0x1800141e3  jz      short loc_180014203
0x1800141e5  test    dword ptr [rcx+1Ch], 20000000h
0x1800141ec  jz      short loc_180014203
0x1800141ee  mov     rcx, [rcx+10h]
0x1800141f2  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x1800141f9  mov     edx, 12h
0x1800141fe  call    WPP_SF_
0x180014203  mov     r9d, 1; unsigned __int16
0x180014209  lea     rdx, aCsppCreateregk; "CSpp::_CreateRegKey"
0x180014210  mov     r8d, 874h; unsigned __int16
0x180014216  lea     rcx, [rbp+57h+var_50]; this
0x18001421a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001421f  mov     [rbp+57h+arg_10], 0
0x180014227  test    rdi, rdi
0x18001422a  jz      short loc_180014233
0x18001422c  mov     qword ptr [rdi], 0
0x180014233  mov     eax, 87Bh
0x180014238  test    rbx, rbx
0x18001423b  jnz     short loc_18001424E
0x18001423d  mov     ebx, 80070057h
0x180014242  mov     [rbp+57h+var_4A], ax
0x180014246  mov     [rbp+57h+var_50], ebx
0x180014249  jmp     loc_1800142F0
0x18001424e  mov     [rbp+57h+var_4C], ax
0x180014252  mov     eax, 87Ch
0x180014257  test    rdi, rdi
0x18001425a  jz      short loc_18001423D
0x18001425c  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x180014265  lea     rcx, [rbp+57h+arg_10]
0x180014269  mov     [rsp+0A0h+phkResult], rcx; phkResult
0x18001426e  xor     r9d, r9d; lpClass
0x180014271  mov     [rbp+57h+var_4C], ax
0x180014275  xor     r8d, r8d; Reserved
0x180014278  lea     rax, [r14+38h]
0x18001427c  mov     [rbp+57h+var_50], 0
0x180014283  mov     [rsp+0A0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180014288  mov     rdx, rbx; lpSubKey
0x18001428b  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x180014293  mov     rcx, rsi; hKey
0x180014296  mov     [rsp+0A0h+dwOptions], 0; dwOptions
0x18001429e  call    cs:__imp_RegCreateKeyExW
0x1800142a4  mov     ebx, eax
0x1800142a6  test    eax, eax
0x1800142a8  jle     short loc_1800142B3
0x1800142aa  movzx   ebx, ax
0x1800142ad  or      ebx, 80070000h
0x1800142b3  mov     [rbp+57h+var_50], ebx
0x1800142b6  mov     eax, 887h
0x1800142bb  test    ebx, ebx
0x1800142bd  jns     short loc_1800142C9
0x1800142bf  mov     rcx, [rbp+57h+arg_10]
0x1800142c3  mov     [rbp+57h+var_4A], ax
0x1800142c7  jmp     short loc_1800142DA
0x1800142c9  mov     [rbp+57h+var_4C], ax
0x1800142cd  xor     ecx, ecx; hKey
0x1800142cf  mov     rax, [rbp+57h+arg_10]
0x1800142d3  mov     [rdi], rax
0x1800142d6  mov     [rbp+57h+arg_10], rcx
0x1800142da  test    rcx, rcx
0x1800142dd  jz      short loc_1800142F0
0x1800142df  call    cs:__imp_RegCloseKey
0x1800142e5  mov     ebx, [rbp+57h+var_50]
0x1800142e8  mov     [rbp+57h+arg_10], 0
0x1800142f0  lea     rcx, [rbp+57h+var_50]; this
0x1800142f4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800142f9  lea     r11, [rsp+0A0h+var_10]
0x180014301  mov     eax, ebx
0x180014303  mov     rbx, [r11+20h]
0x180014307  mov     rsi, [r11+28h]
0x18001430b  mov     rsp, r11
0x18001430e  pop     r14
0x180014310  pop     rdi
0x180014311  pop     rbp
0x180014312  retn
```
