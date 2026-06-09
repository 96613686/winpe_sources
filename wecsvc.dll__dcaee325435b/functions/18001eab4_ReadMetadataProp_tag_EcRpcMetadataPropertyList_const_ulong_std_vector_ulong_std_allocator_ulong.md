# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<ulong,std::allocator<ulong>> &)

- ea: `0x18001eab4`
- end: `0x18001ebbc`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@KV?$allocator@K@std@@@std@@@Z`
- size: `264`
- prototype: `char __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001df44`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001eab4`
- `0x18001f710`

## string_xrefs

- `0x18001eb22`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // r9
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v10; // [rsp+28h] [rbp-40h]
  const char *v11; // [rsp+30h] [rbp-38h]
  __int64 v12; // [rsp+38h] [rbp-30h]
  __int64 v13; // [rsp+40h] [rbp-28h]
  int v14; // [rsp+48h] [rbp-20h]
  int v15; // [rsp+4Ch] [rbp-1Ch]
  int v16; // [rsp+50h] [rbp-18h]

  if ( *(_DWORD *)a1 <= 1u )
    return 0;
  _mm_lfence();
  v5 = *(_QWORD *)(a1 + 8);
  if ( !*(_DWORD *)(v5 + 24) )
    return 0;
  if ( *(_DWORD *)(v5 + 24) != 7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v10 = 0;
    v11 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v12 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v13 = 0;
    v14 = 87;
    v15 = -1;
    v16 = 351;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::vector<unsigned long>::resize(a3, *(unsigned int *)(v5 + 32));
  v6 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v6 + 32) )
  {
    v7 = 0;
    do
    {
      *(_DWORD *)(*a3 + 4 * v7) = *(_DWORD *)(*(_QWORD *)(v6 + 40) + 4 * v7);
      v7 = (unsigned int)(v7 + 1);
      v6 = *(_QWORD *)(a1 + 8);
    }
    while ( (unsigned int)v7 < *(_DWORD *)(v6 + 32) );
  }
  return 1;
}

```

## disassembly

```asm
0x18001eab4  mov     [rsp+arg_0], rbx
0x18001eab9  push    rdi
0x18001eaba  sub     rsp, 60h
0x18001eabe  cmp     dword ptr [rcx], 1
0x18001eac1  mov     rdi, r8
0x18001eac4  mov     rbx, rcx
0x18001eac7  jbe     loc_18001EBAF
0x18001eacd  lfence
0x18001ead0  mov     rax, [rcx+8]
0x18001ead4  cmp     dword ptr [rax+18h], 0
0x18001ead8  jz      loc_18001EBAF
0x18001eade  cmp     dword ptr [rax+18h], 7
0x18001eae2  jz      loc_18001EB77
0x18001eae8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaef  lea     rax, WPP_GLOBAL_Control
0x18001eaf6  mov     ebx, 57h ; 'W'
0x18001eafb  cmp     rcx, rax
0x18001eafe  jz      short loc_18001EB22
0x18001eb00  test    byte ptr [rcx+1Ch], 80h
0x18001eb04  jz      short loc_18001EB22
0x18001eb06  cmp     byte ptr [rcx+19h], 2
0x18001eb0a  jb      short loc_18001EB22
0x18001eb0c  mov     rcx, [rcx+10h]
0x18001eb10  lea     edx, [rbx-45h]
0x18001eb13  mov     r9d, ebx
0x18001eb16  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001eb1d  call    WPP_SF_D
0x18001eb22  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001eb29  mov     [rsp+68h+var_40], 0
0x18001eb2e  mov     [rsp+68h+var_38], rax
0x18001eb33  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001eb3a  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001eb41  mov     [rsp+68h+var_30], 0
0x18001eb4a  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001eb4f  mov     [rsp+68h+pExceptionObject], rax
0x18001eb54  mov     [rsp+68h+var_28], 0
0x18001eb5d  mov     [rsp+68h+var_20], ebx
0x18001eb61  mov     [rsp+68h+var_1C], 0FFFFFFFFh
0x18001eb69  mov     [rsp+68h+var_18], 15Fh
0x18001eb71  call    _CxxThrowException_0
0x18001eb77  mov     edx, [rax+20h]
0x18001eb7a  mov     rcx, rdi
0x18001eb7d  call    ?resize@?$vector@KV?$allocator@K@std@@@std@@QEAAX_K@Z; std::vector<ulong>::resize(unsigned __int64)
0x18001eb82  mov     rcx, [rbx+8]
0x18001eb86  cmp     dword ptr [rcx+20h], 0
0x18001eb8a  jbe     short loc_18001EBAB
0x18001eb8c  xor     r9d, r9d
0x18001eb8f  mov     rcx, [rcx+28h]
0x18001eb93  mov     rdx, [rdi]
0x18001eb96  mov     ecx, [rcx+r9*4]
0x18001eb9a  mov     [rdx+r9*4], ecx
0x18001eb9e  inc     r9d
0x18001eba1  mov     rcx, [rbx+8]
0x18001eba5  cmp     r9d, [rcx+20h]
0x18001eba9  jb      short loc_18001EB8F
0x18001ebab  mov     al, 1
0x18001ebad  jmp     short loc_18001EBB1
0x18001ebaf  xor     al, al
0x18001ebb1  mov     rbx, [rsp+68h+arg_0]
0x18001ebb6  add     rsp, 60h
0x18001ebba  pop     rdi
0x18001ebbb  retn
```
