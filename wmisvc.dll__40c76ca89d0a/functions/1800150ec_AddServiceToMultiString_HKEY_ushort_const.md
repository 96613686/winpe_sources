# AddServiceToMultiString(HKEY__ *,ushort const *)

- ea: `0x1800150ec`
- end: `0x1800152d7`
- name: `?AddServiceToMultiString@@YAJPEAUHKEY__@@PEBG@Z`
- size: `491`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015560`
- `0x180015a00`

## callees

- `0x1800034b8`
- `0x1800039f4`
- `0x18000ca20`
- `0x1800103e0`
- `0x1800150ec`
- `0x180015f78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001512d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015192`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001512d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015192`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015266`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800152b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015266`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800152b5`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015158`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015158`

## pseudocode

```c
__int64 __fastcall AddServiceToMultiString(HKEY hKey, LPCWSTR lpValueName)
{
  int v4; // r15d
  LSTATUS v5; // eax
  unsigned int v6; // edi
  const BYTE *v7; // r14
  BYTE *lpData; // rdx
  DWORD v9; // ecx
  const BYTE *v10; // rdx
  const BYTE *v11; // r12
  __int64 v12; // rbx
  const unsigned __int16 *v13; // r8
  BYTE *v14; // rsi
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+34h] [rbp-Ch] BYREF
  void *v18; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+50h] BYREF

  v4 = 0;
  cbData = 0;
  Type = 0;
  v5 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v6 = v5;
  if ( !v5 )
  {
    cbData += 4;
    SafeInt<unsigned int>::SafeInt<unsigned int>(&v20, cbData + 16LL);
    v7 = (const BYTE *)CWin32DefaultArena::WbemMemAlloc(v20);
    std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(&v18, (__int64)v7);
    if ( !lpData )
    {
      v6 = 14;
      goto LABEL_22;
    }
    v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    if ( v6 )
    {
      if ( Type == 7 )
        goto LABEL_22;
    }
    else if ( Type == 7 )
    {
      v9 = cbData;
      v10 = &v7[cbData];
      v11 = v10 - 2;
      if ( *v7 && cbData > 2 && *((_WORD *)v10 - 2) )
      {
        cbData += 2;
        v11 = v10;
        *(_WORD *)v10 = 0;
        v9 = cbData;
      }
      v12 = *(unsigned int *)SafeInt<unsigned int>::SafeInt<unsigned int>(&v20, v9 + 16LL);
      v14 = (BYTE *)v7;
      if ( *(_WORD *)v7 )
      {
        do
        {
          if ( !(unsigned int)wbem_wcsicmp((const unsigned __int16 *)v14, L"winmgmt") )
            v4 = 1;
          while ( *(_WORD *)v14 )
            v14 += 2;
          v14 += 2;
        }
        while ( *(_WORD *)v14 );
        if ( v4 )
          goto LABEL_22;
      }
      if ( v14 == v11 )
      {
        StringCchCopyNW((unsigned __int16 *)v14, (unsigned __int64)&v7[v12 - (_QWORD)v14] >> 1, v13, 9u);
        *((_WORD *)v14 + 8) = 0;
        v6 = RegSetValueExW(hKey, lpValueName, 0, 7u, v7, v12);
LABEL_22:
        CDeleteMe<unsigned short>::~CDeleteMe<unsigned short>(&v18);
        return v6;
      }
    }
    v6 = 13;
    goto LABEL_22;
  }
  if ( v5 == 2 )
    return (unsigned int)RegSetValueExW(hKey, lpValueName, 0, 7u, L"winmgmt", 0x12u);
  return v6;
}

```

## disassembly

```asm
0x1800150ec  mov     r11, rsp
0x1800150ef  mov     [r11+10h], rbx
0x1800150f3  mov     [r11+8], rcx
0x1800150f7  push    rbp
0x1800150f8  push    rsi
0x1800150f9  push    rdi
0x1800150fa  push    r12
0x1800150fc  push    r13
0x1800150fe  push    r14
0x180015100  push    r15
0x180015102  mov     rbp, rsp
0x180015105  sub     rsp, 40h
0x180015109  mov     r13, rdx
0x18001510c  mov     rbx, rcx
0x18001510f  xor     r15d, r15d
0x180015112  mov     [rbp+cbData], r15d
0x180015116  mov     [rbp+Type], r15d
0x18001511a  lea     rax, [rbp+cbData]
0x18001511e  mov     [r11-50h], rax
0x180015122  mov     [r11-58h], r15
0x180015126  lea     r9, [rbp+Type]; lpType
0x18001512a  xor     r8d, r8d; lpReserved
0x18001512d  call    cs:__imp_RegQueryValueExW
0x180015133  mov     edi, eax
0x180015135  test    eax, eax
0x180015137  jnz     loc_18001528D
0x18001513d  mov     eax, [rbp+cbData]
0x180015140  add     eax, 4
0x180015143  mov     [rbp+cbData], eax
0x180015146  mov     edx, eax
0x180015148  add     rdx, 10h
0x18001514c  lea     rcx, [rbp+arg_10]
0x180015150  call    ??$?0_J@?$SafeInt@I@@QEAA@_J@Z; SafeInt<uint>::SafeInt<uint>(__int64)
0x180015155  mov     ecx, [rbp+arg_10]
0x180015158  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001515e  mov     r14, rax
0x180015161  mov     rdx, rax
0x180015164  lea     rcx, [rbp+var_8]
0x180015168  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x18001516d  nop
0x18001516e  test    rdx, rdx
0x180015171  jz      loc_18001527D
0x180015177  lea     rax, [rbp+cbData]
0x18001517b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180015180  mov     [rsp+40h+lpData], rdx; lpData
0x180015185  lea     r9, [rbp+Type]; lpType
0x180015189  xor     r8d, r8d; lpReserved
0x18001518c  mov     rdx, r13; lpValueName
0x18001518f  mov     rcx, rbx; hKey
0x180015192  call    cs:__imp_RegQueryValueExW
0x180015198  mov     edi, eax
0x18001519a  test    eax, eax
0x18001519c  jnz     loc_180015270
0x1800151a2  cmp     [rbp+Type], 7
0x1800151a6  jnz     loc_180015276
0x1800151ac  mov     ecx, [rbp+cbData]
0x1800151af  lea     rdx, [r14+rcx]
0x1800151b3  lea     r12, [rdx-2]
0x1800151b7  cmp     [r14], r15b
0x1800151ba  jz      short loc_1800151D9
0x1800151bc  cmp     ecx, 2
0x1800151bf  jbe     short loc_1800151D9
0x1800151c1  cmp     r15w, [r12-2]
0x1800151c7  jz      short loc_1800151D9
0x1800151c9  add     ecx, 2
0x1800151cc  mov     [rbp+cbData], ecx
0x1800151cf  mov     r12, rdx
0x1800151d2  mov     [rdx], r15w
0x1800151d6  mov     ecx, [rbp+cbData]
0x1800151d9  mov     edx, ecx
0x1800151db  add     rdx, 10h
0x1800151df  lea     rcx, [rbp+arg_10]
0x1800151e3  call    ??$?0_J@?$SafeInt@I@@QEAA@_J@Z; SafeInt<uint>::SafeInt<uint>(__int64)
0x1800151e8  mov     ebx, [rax]
0x1800151ea  mov     rsi, r14
0x1800151ed  xor     eax, eax
0x1800151ef  cmp     [r14], ax
0x1800151f3  jz      short loc_18001522A
0x1800151f5  lea     rdx, ServiceName; "winmgmt"
0x1800151fc  mov     rcx, rsi; unsigned __int16 *
0x1800151ff  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x180015204  mov     ecx, 1
0x180015209  xor     edx, edx
0x18001520b  test    eax, eax
0x18001520d  cmovz   r15d, ecx
0x180015211  jmp     short loc_180015217
0x180015213  add     rsi, 2
0x180015217  cmp     [rsi], dx
0x18001521a  jnz     short loc_180015213
0x18001521c  add     rsi, 2
0x180015220  cmp     [rsi], dx
0x180015223  jnz     short loc_1800151F5
0x180015225  test    r15d, r15d
0x180015228  jnz     short loc_180015282
0x18001522a  cmp     rsi, r12
0x18001522d  jnz     short loc_180015276
0x18001522f  mov     rdx, rbx
0x180015232  sub     rdx, rsi
0x180015235  add     rdx, r14
0x180015238  shr     rdx, 1; unsigned __int64
0x18001523b  mov     r9d, 9; unsigned __int64
0x180015241  mov     rcx, rsi; unsigned __int16 *
0x180015244  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180015249  xor     eax, eax
0x18001524b  mov     [rsi+10h], ax
0x18001524f  mov     dword ptr [rsp+40h+lpcbData], ebx; cbData
0x180015253  mov     [rsp+40h+lpData], r14; lpData
0x180015258  lea     r9d, [rax+7]; dwType
0x18001525c  xor     r8d, r8d; Reserved
0x18001525f  mov     rdx, r13; lpValueName
0x180015262  mov     rcx, [rbp+hKey]; hKey
0x180015266  call    cs:__imp_RegSetValueExW
0x18001526c  mov     edi, eax
0x18001526e  jmp     short loc_180015282
0x180015270  cmp     [rbp+Type], 7
0x180015274  jz      short loc_180015282
0x180015276  mov     edi, 0Dh
0x18001527b  jmp     short loc_180015282
0x18001527d  mov     edi, 0Eh
0x180015282  lea     rcx, [rbp+var_8]
0x180015286  call    ??1?$CDeleteMe@G@@QEAA@XZ; CDeleteMe<ushort>::~CDeleteMe<ushort>(void)
0x18001528b  jmp     short loc_1800152BD
0x18001528d  cmp     eax, 2
0x180015290  jnz     short loc_1800152BD
0x180015292  mov     dword ptr [rsp+40h+lpcbData], 12h; cbData
0x18001529a  lea     rax, Data; "winmgmt"
0x1800152a1  mov     [rsp+40h+lpData], rax; lpData
0x1800152a6  mov     r9d, 7; dwType
0x1800152ac  xor     r8d, r8d; Reserved
0x1800152af  mov     rdx, r13; lpValueName
0x1800152b2  mov     rcx, rbx; hKey
0x1800152b5  call    cs:__imp_RegSetValueExW
0x1800152bb  mov     edi, eax
0x1800152bd  mov     eax, edi
0x1800152bf  mov     rbx, [rsp+40h+arg_8]
0x1800152c7  add     rsp, 40h
0x1800152cb  pop     r15
0x1800152cd  pop     r14
0x1800152cf  pop     r13
0x1800152d1  pop     r12
0x1800152d3  pop     rdi
0x1800152d4  pop     rsi
0x1800152d5  pop     rbp
0x1800152d6  retn
```
