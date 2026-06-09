# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18001ebc4`
- end: `0x18001ece4`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `288`
- prototype: `char __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001df44`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000669c`
- `0x18001ebc4`
- `0x18001f7ac`

## string_xrefs

- `0x18001ec36`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(__int64 a1, unsigned int a2, _QWORD *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rbp
  __int64 v9; // rax
  const wchar_t *v10; // rdx
  void **pExceptionObject; // [rsp+20h] [rbp-68h] BYREF
  char v13; // [rsp+28h] [rbp-60h]
  const char *v14; // [rsp+30h] [rbp-58h]
  __int64 v15; // [rsp+38h] [rbp-50h]
  __int64 v16; // [rsp+40h] [rbp-48h]
  int v17; // [rsp+48h] [rbp-40h]
  int v18; // [rsp+4Ch] [rbp-3Ch]
  int v19; // [rsp+50h] [rbp-38h]

  if ( a2 >= *(_DWORD *)a1 )
    return 0;
  _mm_lfence();
  v5 = 3LL * a2;
  v6 = *(_QWORD *)(a1 + 8);
  if ( !*(_DWORD *)(v6 + 24LL * a2) )
    return 0;
  if ( *(_DWORD *)(v6 + 24LL * a2) != 6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v13 = 0;
    v14 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v15 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v16 = 0;
    v17 = 87;
    v18 = -1;
    v19 = 374;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::vector<std::wstring>::resize(a3, *(unsigned int *)(v6 + 24LL * a2 + 8));
  v7 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v7 + 8 * v5 + 8) )
  {
    v8 = 0;
    do
    {
      v9 = *(_QWORD *)(v7 + 8 * v5 + 16);
      v10 = &word_180026AD8;
      if ( *(_QWORD *)(v9 + 8 * v8) )
        v10 = *(const wchar_t **)(v9 + 8 * v8);
      std::wstring::assign(*a3 + 32LL * (unsigned int)v8, v10);
      v7 = *(_QWORD *)(a1 + 8);
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < *(_DWORD *)(v7 + 8 * v5 + 8) );
  }
  return 1;
}

```

## disassembly

```asm
0x18001ebc4  push    rbx
0x18001ebc6  push    rbp
0x18001ebc7  push    rsi
0x18001ebc8  push    rdi
0x18001ebc9  sub     rsp, 68h
0x18001ebcd  mov     rsi, r8
0x18001ebd0  mov     rbx, rcx
0x18001ebd3  cmp     edx, [rcx]
0x18001ebd5  jnb     loc_18001ECD9
0x18001ebdb  lfence
0x18001ebde  mov     eax, edx
0x18001ebe0  lea     rdi, [rax+rax*2]
0x18001ebe4  mov     rax, [rcx+8]
0x18001ebe8  cmp     dword ptr [rax+rdi*8], 0
0x18001ebec  jz      loc_18001ECD9
0x18001ebf2  cmp     dword ptr [rax+rdi*8], 6
0x18001ebf6  jz      loc_18001EC8B
0x18001ebfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec03  lea     rax, WPP_GLOBAL_Control
0x18001ec0a  mov     ebx, 57h ; 'W'
0x18001ec0f  cmp     rcx, rax
0x18001ec12  jz      short loc_18001EC36
0x18001ec14  test    byte ptr [rcx+1Ch], 80h
0x18001ec18  jz      short loc_18001EC36
0x18001ec1a  cmp     byte ptr [rcx+19h], 2
0x18001ec1e  jb      short loc_18001EC36
0x18001ec20  mov     rcx, [rcx+10h]
0x18001ec24  lea     edx, [rbx-44h]
0x18001ec27  mov     r9d, ebx
0x18001ec2a  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001ec31  call    WPP_SF_D
0x18001ec36  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ec3d  mov     [rsp+88h+var_60], 0
0x18001ec42  mov     [rsp+88h+var_58], rax
0x18001ec47  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ec4e  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ec55  mov     [rsp+88h+var_50], 0
0x18001ec5e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001ec63  mov     [rsp+88h+pExceptionObject], rax
0x18001ec68  mov     [rsp+88h+var_48], 0
0x18001ec71  mov     [rsp+88h+var_40], ebx
0x18001ec75  mov     [rsp+88h+var_3C], 0FFFFFFFFh
0x18001ec7d  mov     [rsp+88h+var_38], 176h
0x18001ec85  call    _CxxThrowException_0
0x18001ec8b  mov     edx, [rax+rdi*8+8]
0x18001ec8f  mov     rcx, rsi
0x18001ec92  call    ?resize@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::wstring>::resize(unsigned __int64)
0x18001ec97  mov     rax, [rbx+8]
0x18001ec9b  cmp     dword ptr [rax+rdi*8+8], 0
0x18001eca0  jbe     short loc_18001ECD5
0x18001eca2  xor     ebp, ebp
0x18001eca4  mov     rax, [rax+rdi*8+10h]
0x18001eca9  lea     rdx, word_180026AD8
0x18001ecb0  mov     ecx, ebp
0x18001ecb2  shl     rcx, 5
0x18001ecb6  add     rcx, [rsi]
0x18001ecb9  mov     r8, [rax+rbp*8]
0x18001ecbd  test    r8, r8
0x18001ecc0  cmovnz  rdx, r8
0x18001ecc4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001ecc9  mov     rax, [rbx+8]
0x18001eccd  inc     ebp
0x18001eccf  cmp     ebp, [rax+rdi*8+8]
0x18001ecd3  jb      short loc_18001ECA4
0x18001ecd5  mov     al, 1
0x18001ecd7  jmp     short loc_18001ECDB
0x18001ecd9  xor     al, al
0x18001ecdb  add     rsp, 68h
0x18001ecdf  pop     rdi
0x18001ece0  pop     rsi
0x18001ece1  pop     rbp
0x18001ece2  pop     rbx
0x18001ece3  retn
```
