# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<ushort,std::allocator<ushort>> &)

- ea: `0x18001e8f0`
- end: `0x18001eaac`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `444`
- prototype: `char __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ddec`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180005d08`
- `0x1800112e8`
- `0x180012ddc`
- `0x18001e8f0`

## string_xrefs

- `0x18001e96b`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`
- `0x18001ea3c`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(__int64 a1, int a2, __int64 a3)
{
  int v5; // ecx
  __int64 v6; // rcx
  __int64 v7; // rbx
  int v8; // ebx
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v11; // [rsp+28h] [rbp-38h]
  const char *v12; // [rsp+30h] [rbp-30h]
  __int64 v13; // [rsp+38h] [rbp-28h]
  __int64 v14; // [rsp+40h] [rbp-20h]
  int v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+4Ch] [rbp-14h]
  int v17; // [rsp+50h] [rbp-10h]
  int v18; // [rsp+88h] [rbp+28h] BYREF

  v18 = a2;
  if ( *(_DWORD *)a1 <= 0x17u )
    return 0;
  v5 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 552LL);
  if ( !v5 )
    return 0;
  if ( v5 != 4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v11 = 0;
    v12 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v13 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v14 = 0;
    v15 = 87;
    v16 = -1;
    v17 = 279;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  *(_QWORD *)(a3 + 8) = *(_QWORD *)a3;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 560LL);
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
    std::vector<unsigned short>::resize(a3, v7 + 1);
    v8 = StringCchCopyW(*(unsigned __int16 **)a3, v7 + 1, *(const unsigned __int16 **)(*(_QWORD *)(a1 + 8) + 560LL));
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_1484ca0113be328fb1dd317c070a3401_Traceguids,
          (unsigned int)v8);
      }
      v11 = 0;
      v12 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
      v13 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v14 = 0;
      v15 = v8;
      v16 = -1;
      v17 = 289;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  else
  {
    LOWORD(v18) = 0;
    std::vector<unsigned short>::push_back(a3, &v18);
  }
  return 1;
}

```

## disassembly

```asm
0x18001e8f0  mov     [rsp-18h+arg_0], rbx
0x18001e8f5  mov     [rsp-18h+arg_10], rsi
0x18001e8fa  mov     [rsp-18h+arg_8], edx
0x18001e8fe  push    rbp
0x18001e8ff  push    rdi
0x18001e900  push    r14
0x18001e902  mov     rbp, rsp
0x18001e905  sub     rsp, 60h
0x18001e909  cmp     dword ptr [rcx], 17h
0x18001e90c  mov     rdi, r8
0x18001e90f  mov     rsi, rcx
0x18001e912  jbe     loc_18001EA95
0x18001e918  mov     rax, [rcx+8]
0x18001e91c  xor     r14d, r14d
0x18001e91f  mov     ecx, [rax+228h]
0x18001e925  test    ecx, ecx
0x18001e927  jz      loc_18001EA95
0x18001e92d  cmp     ecx, 4
0x18001e930  jz      short loc_18001E9AF
0x18001e932  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e939  lea     rax, WPP_GLOBAL_Control
0x18001e940  lea     ebx, [r14+57h]
0x18001e944  cmp     rcx, rax
0x18001e947  jz      short loc_18001E96B
0x18001e949  test    byte ptr [rcx+1Ch], 80h
0x18001e94d  jz      short loc_18001E96B
0x18001e94f  cmp     byte ptr [rcx+19h], 2
0x18001e953  jb      short loc_18001E96B
0x18001e955  mov     rcx, [rcx+10h]
0x18001e959  lea     edx, [rbx-49h]
0x18001e95c  mov     r9d, ebx
0x18001e95f  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001e966  call    WPP_SF_D
0x18001e96b  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001e972  mov     [rbp+var_38], r14b
0x18001e976  mov     [rbp+var_30], rax
0x18001e97a  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001e981  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001e988  mov     [rbp+var_28], r14
0x18001e98c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e990  mov     [rbp+pExceptionObject], rax
0x18001e994  mov     [rbp+var_20], r14
0x18001e998  mov     [rbp+var_18], ebx
0x18001e99b  mov     [rbp+var_14], 0FFFFFFFFh
0x18001e9a2  mov     [rbp+var_10], 117h
0x18001e9a9  call    _CxxThrowException_0
0x18001e9af  mov     rax, [r8]
0x18001e9b2  mov     [r8+8], rax
0x18001e9b6  mov     rax, [rsi+8]
0x18001e9ba  mov     rcx, [rax+230h]
0x18001e9c1  test    rcx, rcx
0x18001e9c4  jz      loc_18001EA80
0x18001e9ca  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001e9ce  inc     rbx
0x18001e9d1  cmp     [rcx+rbx*2], r14w
0x18001e9d6  jnz     short loc_18001E9CE
0x18001e9d8  lea     rdx, [rbx+1]
0x18001e9dc  mov     rcx, rdi
0x18001e9df  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001e9e4  mov     r8, [rsi+8]
0x18001e9e8  lea     rdx, [rbx+1]; unsigned __int64
0x18001e9ec  mov     rcx, [rdi]; unsigned __int16 *
0x18001e9ef  mov     r8, [r8+230h]; unsigned __int16 *
0x18001e9f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e9fb  mov     ebx, eax
0x18001e9fd  test    eax, eax
0x18001e9ff  jns     loc_18001EA91
0x18001ea05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea0c  lea     rax, WPP_GLOBAL_Control
0x18001ea13  cmp     rcx, rax
0x18001ea16  jz      short loc_18001EA3C
0x18001ea18  test    byte ptr [rcx+1Ch], 80h
0x18001ea1c  jz      short loc_18001EA3C
0x18001ea1e  cmp     byte ptr [rcx+19h], 2
0x18001ea22  jb      short loc_18001EA3C
0x18001ea24  mov     rcx, [rcx+10h]
0x18001ea28  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001ea2f  mov     edx, 0Fh
0x18001ea34  mov     r9d, ebx
0x18001ea37  call    WPP_SF_D
0x18001ea3c  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ea43  mov     [rbp+var_38], r14b
0x18001ea47  mov     [rbp+var_30], rax
0x18001ea4b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ea52  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ea59  mov     [rbp+var_28], r14
0x18001ea5d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001ea61  mov     [rbp+pExceptionObject], rax
0x18001ea65  mov     [rbp+var_20], r14
0x18001ea69  mov     [rbp+var_18], ebx
0x18001ea6c  mov     [rbp+var_14], 0FFFFFFFFh
0x18001ea73  mov     [rbp+var_10], 121h
0x18001ea7a  call    _CxxThrowException_0
0x18001ea80  lea     rdx, [rbp+arg_8]
0x18001ea84  mov     word ptr [rbp+arg_8], r14w
0x18001ea89  mov     rcx, rdi
0x18001ea8c  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001ea91  mov     al, 1
0x18001ea93  jmp     short loc_18001EA97
0x18001ea95  xor     al, al
0x18001ea97  lea     r11, [rsp+60h+var_s0]
0x18001ea9c  mov     rbx, [r11+20h]
0x18001eaa0  mov     rsi, [r11+30h]
0x18001eaa4  mov     rsp, r11
0x18001eaa7  pop     r14
0x18001eaa9  pop     rdi
0x18001eaaa  pop     rbp
0x18001eaab  retn
```
