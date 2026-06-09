# GetRegSettingsBool(HKEY__ *,ushort const *,bool *)

- ea: `0x14001550c`
- end: `0x14001578d`
- name: `?GetRegSettingsBool@@YAJPEAUHKEY__@@PEBGPEA_N@Z`
- size: `641`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a358`
- `0x14000a3f8`
- `0x140010d64`

## callees

- `0x140001338`
- `0x140014404`
- `0x14001550c`
- `0x1400175a0`
- `0x1400175d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140015603`
- `KERNEL32!GetLastError` at `0x140015603`
- `KERNEL32!MultiByteToWideChar` at `0x1400156f2`
- `KERNEL32!MultiByteToWideChar` at `0x1400156f2`
- `KERNEL32!WideCharToMultiByte` at `0x1400155f6`
- `KERNEL32!WideCharToMultiByte` at `0x14001565c`
- `KERNEL32!WideCharToMultiByte` at `0x1400155f6`
- `KERNEL32!WideCharToMultiByte` at `0x14001565c`
- `ADVAPI32!RegQueryValueExA` at `0x140015690`
- `ADVAPI32!RegQueryValueExA` at `0x140015690`
- `ADVAPI32!RegQueryValueExW` at `0x14001557f`
- `ADVAPI32!RegQueryValueExW` at `0x14001557f`

## pseudocode

```c
signed int __fastcall GetRegSettingsBool(HKEY hKey, LPCWCH lpWideCharStr, bool *a3)
{
  bool v6; // bl
  signed int result; // eax
  bool v8; // cc
  BYTE *v9; // rdi
  int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  DWORD *p_cbData; // rsi
  DWORD v16; // ecx
  __int64 v17; // rax
  DWORD cbData; // [rsp+40h] [rbp+0h] BYREF
  DWORD Type[3]; // [rsp+44h] [rbp+4h] BYREF
  CHAR lpData[1024]; // [rsp+50h] [rbp+10h] BYREF
  WCHAR Data[1024]; // [rsp+450h] [rbp+410h] BYREF

  Type[0] = 0;
  cbData = 0;
  v6 = 1;
  if ( Global::g_fWindowsNT )
  {
    cbData = 1024;
    result = RegQueryValueExW(hKey, lpWideCharStr, 0, Type, (LPBYTE)Data, &cbData);
    v8 = result <= 0;
    if ( result )
      goto LABEL_3;
    v9 = (BYTE *)Data;
    goto LABEL_22;
  }
  if ( lpWideCharStr )
  {
    v10 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v10 )
      goto LABEL_9;
    v11 = v10 + 15LL;
    if ( v11 < v10 )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = alloca(v12);
    v14 = alloca(v12);
    p_cbData = &cbData;
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, (LPSTR)&cbData, v10, 0, 0) )
      goto LABEL_9;
  }
  else
  {
    p_cbData = 0;
  }
  cbData = 1024;
  result = RegQueryValueExA(hKey, (LPCSTR)p_cbData, 0, Type, (LPBYTE)lpData, &cbData);
  v8 = result <= 0;
  if ( result )
  {
LABEL_3:
    if ( !v8 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v16 = cbData;
  if ( !cbData )
    return -2147467259;
  v17 = cbData - 1;
  if ( (unsigned int)v17 >= 0x400 )
    _report_rangecheckfailure();
  lpData[v17] = 0;
  if ( Type[0] - 1 > 1 )
  {
    v9 = (BYTE *)lpData;
    goto LABEL_23;
  }
  v9 = 0;
  if ( !MultiByteToWideChar(0, 0, lpData, -1, Data, 1024) )
  {
LABEL_9:
    result = GetLastError();
    v8 = result <= 0;
    goto LABEL_3;
  }
LABEL_22:
  v16 = cbData;
LABEL_23:
  if ( Type[0] == 1 || Type[0] == 2 )
  {
    *a3 = 1;
    if ( !(unsigned int)CompareStrsCaseInsensitive(Data, L"0", 0xFFFFFFFFFFFFFFFFuLL)
      || !(unsigned int)CompareStrsCaseInsensitive(Data, L"no", 0xFFFFFFFFFFFFFFFFuLL)
      || !(unsigned int)CompareStrsCaseInsensitive(Data, L"false", 0xFFFFFFFFFFFFFFFFuLL) )
    {
      v6 = 0;
    }
  }
  else
  {
    if ( Type[0] != 4 || v16 != 4 )
      return -2147221165;
    v6 = *(_DWORD *)v9 != 0;
  }
  *a3 = v6;
  return 0;
}

```

## disassembly

```asm
0x14001550c  push    rbp
0x14001550e  push    rbx
0x14001550f  push    rsi
0x140015510  push    rdi
0x140015511  push    r13
0x140015513  push    r14
0x140015515  push    r15
0x140015517  sub     rsp, 0C60h
0x14001551e  lea     rbp, [rsp+40h]
0x140015523  mov     rax, cs:__security_cookie
0x14001552a  xor     rax, rbp
0x14001552d  mov     [rbp+0C50h+var_40], rax
0x140015534  or      r13, 0FFFFFFFFFFFFFFFFh
0x140015538  mov     [rbp+0C50h+Type], 0
0x14001553f  cmp     cs:?g_fWindowsNT@Global@@2_NA, 0; bool Global::g_fWindowsNT
0x140015546  mov     r14, r8
0x140015549  mov     rdi, rdx
0x14001554c  mov     [rbp+0C50h+cbData], 0
0x140015553  mov     r15, rcx
0x140015556  lea     ebx, [r13+2]
0x14001555a  jz      short loc_1400155C0
0x14001555c  lea     rax, [rbp+0C50h+cbData]
0x140015560  mov     [rbp+0C50h+cbData], 400h
0x140015567  mov     [rsp+0C90h+lpcbData], rax; lpcbData
0x14001556c  lea     r9, [rbp+0C50h+Type]; lpType
0x140015570  lea     rax, [rbp+0C50h+Data]
0x140015577  xor     r8d, r8d; lpReserved
0x14001557a  mov     [rsp+0C90h+lpData], rax; lpData
0x14001557f  call    cs:__imp_RegQueryValueExW
0x140015585  test    eax, eax
0x140015587  jz      short loc_1400155B4
0x140015589  jle     short loc_140015593
0x14001558b  movzx   eax, ax
0x14001558e  or      eax, 80070000h
0x140015593  mov     rcx, [rbp+0C50h+var_40]
0x14001559a  xor     rcx, rbp; StackCookie
0x14001559d  call    __security_check_cookie
0x1400155a2  lea     rsp, [rbp+0C20h]
0x1400155a9  pop     r15
0x1400155ab  pop     r14
0x1400155ad  pop     r13
0x1400155af  pop     rdi
0x1400155b0  pop     rsi
0x1400155b1  pop     rbx
0x1400155b2  pop     rbp
0x1400155b3  retn
0x1400155b4  lea     rdi, [rbp+0C50h+Data]
0x1400155bb  jmp     loc_140015700
0x1400155c0  test    rdi, rdi
0x1400155c3  jz      loc_140015668
0x1400155c9  mov     [rsp+0C90h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400155d2  mov     r9d, r13d; cchWideChar
0x1400155d5  mov     [rsp+0C90h+lpDefaultChar], 0; lpDefaultChar
0x1400155de  mov     r8, rdi; lpWideCharStr
0x1400155e1  mov     dword ptr [rsp+0C90h+lpcbData], 0; cbMultiByte
0x1400155e9  xor     edx, edx; dwFlags
0x1400155eb  xor     ecx, ecx; CodePage
0x1400155ed  mov     [rsp+0C90h+lpData], 0; lpMultiByteStr
0x1400155f6  call    cs:__imp_WideCharToMultiByte
0x1400155fc  movsxd  rdx, eax
0x1400155ff  test    eax, eax
0x140015601  jnz     short loc_140015610
0x140015603  call    cs:__imp_GetLastError
0x140015609  test    eax, eax
0x14001560b  jmp     loc_140015589
0x140015610  lea     rcx, [rdx+0Fh]
0x140015614  cmp     rcx, rdx
0x140015617  ja      short loc_140015623
0x140015619  mov     rcx, 0FFFFFFFFFFFFFF0h
0x140015623  and     rcx, 0FFFFFFFFFFFFFFF0h
0x140015627  mov     rax, rcx
0x14001562a  call    _alloca_probe
0x14001562f  sub     rsp, rcx
0x140015632  mov     r9d, r13d; cchWideChar
0x140015635  mov     r8, rdi; lpWideCharStr
0x140015638  xor     ecx, ecx; CodePage
0x14001563a  mov     [rsp+0C90h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140015643  lea     rsi, [rsp+0C90h+cbData]
0x140015648  mov     [rsp+0C90h+lpDefaultChar], 0; lpDefaultChar
0x140015651  mov     dword ptr [rsp+0C90h+lpcbData], edx; cbMultiByte
0x140015655  xor     edx, edx; dwFlags
0x140015657  mov     [rsp+0C90h+lpData], rsi; lpMultiByteStr
0x14001565c  call    cs:__imp_WideCharToMultiByte
0x140015662  test    eax, eax
0x140015664  jnz     short loc_14001566A
0x140015666  jmp     short loc_140015603
0x140015668  xor     esi, esi
0x14001566a  lea     rax, [rbp+0C50h+cbData]
0x14001566e  mov     [rbp+0C50h+cbData], 400h
0x140015675  mov     [rsp+0C90h+lpcbData], rax; lpcbData
0x14001567a  lea     r9, [rbp+0C50h+Type]; lpType
0x14001567e  lea     rax, [rbp+0C50h+var_C40]
0x140015682  xor     r8d, r8d; lpReserved
0x140015685  mov     rdx, rsi; lpValueName
0x140015688  mov     [rsp+0C90h+lpData], rax; lpData
0x14001568d  mov     rcx, r15; hKey
0x140015690  call    cs:__imp_RegQueryValueExA
0x140015696  test    eax, eax
0x140015698  jnz     loc_140015589
0x14001569e  mov     ecx, [rbp+0C50h+cbData]
0x1400156a1  test    ecx, ecx
0x1400156a3  jnz     short loc_1400156AF
0x1400156a5  mov     eax, 80004005h
0x1400156aa  jmp     loc_140015593
0x1400156af  lea     eax, [rcx-1]
0x1400156b2  cmp     eax, 400h
0x1400156b7  jnb     loc_140015787
0x1400156bd  mov     [rbp+rax+0C50h+var_C40], 0
0x1400156c2  mov     eax, [rbp+0C50h+Type]
0x1400156c5  dec     eax
0x1400156c7  cmp     eax, ebx
0x1400156c9  jbe     short loc_1400156D1
0x1400156cb  lea     rdi, [rbp+0C50h+var_C40]
0x1400156cf  jmp     short loc_140015703
0x1400156d1  lea     rax, [rbp+0C50h+Data]
0x1400156d8  mov     dword ptr [rsp+0C90h+lpcbData], 400h; cchWideChar
0x1400156e0  mov     r9d, r13d; cbMultiByte
0x1400156e3  mov     [rsp+0C90h+lpData], rax; lpWideCharStr
0x1400156e8  lea     r8, [rbp+0C50h+var_C40]; lpMultiByteStr
0x1400156ec  xor     edx, edx; dwFlags
0x1400156ee  xor     ecx, ecx; CodePage
0x1400156f0  xor     edi, edi
0x1400156f2  call    cs:__imp_MultiByteToWideChar
0x1400156f8  test    eax, eax
0x1400156fa  jz      loc_140015603
0x140015700  mov     ecx, [rbp+0C50h+cbData]
0x140015703  mov     eax, [rbp+0C50h+Type]
0x140015706  sub     eax, ebx
0x140015708  jz      short loc_14001572A
0x14001570a  sub     eax, ebx
0x14001570c  jz      short loc_14001572A
0x14001570e  cmp     eax, 2
0x140015711  jnz     short loc_140015720
0x140015713  cmp     ecx, 4
0x140015716  jnz     short loc_140015720
0x140015718  cmp     dword ptr [rdi], 0
0x14001571b  setnz   bl
0x14001571e  jmp     short loc_14001577D
0x140015720  mov     eax, 80040153h
0x140015725  jmp     loc_140015593
0x14001572a  mov     r8, r13; unsigned __int64
0x14001572d  mov     [r14], bl
0x140015730  lea     rdx, a0; "0"
0x140015737  lea     rcx, [rbp+0C50h+Data]; unsigned __int16 *
0x14001573e  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x140015743  test    eax, eax
0x140015745  jz      short loc_14001577B
0x140015747  mov     r8, r13; unsigned __int64
0x14001574a  lea     rdx, aNo_0; "no"
0x140015751  lea     rcx, [rbp+0C50h+Data]; unsigned __int16 *
0x140015758  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x14001575d  test    eax, eax
0x14001575f  jz      short loc_14001577B
0x140015761  mov     r8, r13; unsigned __int64
0x140015764  lea     rdx, aFalse; "false"
0x14001576b  lea     rcx, [rbp+0C50h+Data]; unsigned __int16 *
0x140015772  call    ?CompareStrsCaseInsensitive@@YAHPEBG0_K@Z; CompareStrsCaseInsensitive(ushort const *,ushort const *,unsigned __int64)
0x140015777  test    eax, eax
0x140015779  jnz     short loc_14001577D
0x14001577b  xor     bl, bl
0x14001577d  mov     [r14], bl
0x140015780  xor     eax, eax
0x140015782  jmp     loc_140015593
0x140015787  call    __report_rangecheckfailure
```
