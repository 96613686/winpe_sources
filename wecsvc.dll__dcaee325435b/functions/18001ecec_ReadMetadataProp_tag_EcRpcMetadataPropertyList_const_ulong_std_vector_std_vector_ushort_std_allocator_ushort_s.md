# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<std::vector<ushort,std::allocator<ushort>>,std::allocator<std::vector<ushort,std::allocator<ushort>>>> &)

- ea: `0x18001ecec`
- end: `0x18001eee6`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@@Z`
- size: `506`
- prototype: `char __fastcall(__int64, int, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001df44`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180005d08`
- `0x1800112e8`
- `0x180012ddc`
- `0x18001ecec`
- `0x18001f850`

## string_xrefs

- `0x18001ed65`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`
- `0x18001ee63`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(__int64 a1, int a2, __int64 *a3)
{
  __int64 v5; // rax
  unsigned int i; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbx
  int v10; // ebx
  __int64 v11; // rcx
  void **pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  char v14; // [rsp+28h] [rbp-40h]
  const char *v15; // [rsp+30h] [rbp-38h]
  __int64 v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h]
  int v18; // [rsp+48h] [rbp-20h]
  int v19; // [rsp+4Ch] [rbp-1Ch]
  int v20; // [rsp+50h] [rbp-18h]
  int v21; // [rsp+B8h] [rbp+50h] BYREF

  v21 = a2;
  if ( *(_DWORD *)a1 <= 5u )
    return 0;
  _mm_lfence();
  v5 = *(_QWORD *)(a1 + 8);
  if ( !*(_DWORD *)(v5 + 120) )
    return 0;
  if ( *(_DWORD *)(v5 + 120) != 6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v14 = 0;
    v15 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v16 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v17 = 0;
    v18 = 87;
    v19 = -1;
    v20 = 404;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::vector<std::vector<unsigned short>>::resize(a3, *(unsigned int *)(v5 + 128));
  for ( i = 0; ; ++i )
  {
    v7 = *(_QWORD *)(a1 + 8);
    if ( i >= *(_DWORD *)(v7 + 128) )
      break;
    v8 = *(_QWORD *)(*(_QWORD *)(v7 + 136) + 8LL * i);
    if ( v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( *(_WORD *)(v8 + 2 * v9) );
      std::vector<unsigned short>::resize(*a3 + 24LL * i, v9 + 1);
      v10 = StringCchCopyW(
              *(unsigned __int16 **)(*a3 + 24LL * i),
              v9 + 1,
              *(const unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 136LL) + 8LL * i));
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_1484ca0113be328fb1dd317c070a3401_Traceguids,
            (unsigned int)v10);
        }
        v14 = 0;
        v15 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
        v16 = 0;
        pExceptionObject = &wmi::GenericException::`vftable';
        v17 = 0;
        v18 = v10;
        v19 = -1;
        v20 = 420;
        throw (wmi::GenericException *)&pExceptionObject;
      }
    }
    else
    {
      v11 = *a3;
      LOWORD(v21) = 0;
      *(_QWORD *)(v11 + 24LL * i + 8) = *(_QWORD *)(v11 + 24LL * i);
      std::vector<unsigned short>::push_back(*a3 + 24LL * i, &v21);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001ecec  mov     [rsp-40h+arg_8], edx
0x18001ecf0  push    rbp
0x18001ecf1  push    rbx
0x18001ecf2  push    rsi
0x18001ecf3  push    rdi
0x18001ecf4  push    r12
0x18001ecf6  push    r13
0x18001ecf8  push    r14
0x18001ecfa  push    r15
0x18001ecfc  mov     rbp, rsp
0x18001ecff  sub     rsp, 68h
0x18001ed03  cmp     dword ptr [rcx], 5
0x18001ed06  mov     r14, r8
0x18001ed09  mov     rsi, rcx
0x18001ed0c  jbe     loc_18001EED3
0x18001ed12  lfence
0x18001ed15  mov     rax, [rcx+8]
0x18001ed19  xor     r13d, r13d
0x18001ed1c  cmp     [rax+78h], r13d
0x18001ed20  jz      loc_18001EED3
0x18001ed26  cmp     dword ptr [rax+78h], 6
0x18001ed2a  jz      short loc_18001EDA9
0x18001ed2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed33  lea     rax, WPP_GLOBAL_Control
0x18001ed3a  lea     ebx, [r13+57h]
0x18001ed3e  cmp     rcx, rax
0x18001ed41  jz      short loc_18001ED65
0x18001ed43  test    byte ptr [rcx+1Ch], 80h
0x18001ed47  jz      short loc_18001ED65
0x18001ed49  cmp     byte ptr [rcx+19h], 2
0x18001ed4d  jb      short loc_18001ED65
0x18001ed4f  mov     rcx, [rcx+10h]
0x18001ed53  lea     edx, [rbx-43h]
0x18001ed56  mov     r9d, ebx
0x18001ed59  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001ed60  call    WPP_SF_D
0x18001ed65  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ed6c  mov     [rbp+var_40], r13b
0x18001ed70  mov     [rbp+var_38], rax
0x18001ed74  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ed7b  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ed82  mov     [rbp+var_30], r13
0x18001ed86  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001ed8a  mov     [rbp+pExceptionObject], rax
0x18001ed8e  mov     [rbp+var_28], r13
0x18001ed92  mov     [rbp+var_20], ebx
0x18001ed95  mov     [rbp+var_1C], 0FFFFFFFFh
0x18001ed9c  mov     [rbp+var_18], 194h
0x18001eda3  call    _CxxThrowException_0
0x18001eda9  mov     edx, [rax+80h]
0x18001edaf  mov     rcx, r14
0x18001edb2  call    ?resize@?$vector@V?$vector@GV?$allocator@G@std@@@std@@V?$allocator@V?$vector@GV?$allocator@G@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::vector<ushort>>::resize(unsigned __int64)
0x18001edb7  mov     edi, r13d
0x18001edba  mov     rax, [rsi+8]
0x18001edbe  cmp     edi, [rax+80h]
0x18001edc4  jnb     loc_18001EECF
0x18001edca  mov     rax, [rax+88h]
0x18001edd1  mov     r12d, edi
0x18001edd4  mov     rcx, [rax+r12*8]
0x18001edd8  lea     r15, [r12+r12*2]
0x18001eddc  test    rcx, rcx
0x18001eddf  jz      loc_18001EEA7
0x18001ede5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001ede9  inc     rbx
0x18001edec  cmp     [rcx+rbx*2], r13w
0x18001edf1  jnz     short loc_18001EDE9
0x18001edf3  mov     rax, [r14]
0x18001edf6  lea     rdx, [rbx+1]
0x18001edfa  lea     rcx, [rax+r15*8]
0x18001edfe  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18001ee03  mov     rax, [rsi+8]
0x18001ee07  lea     rdx, [rbx+1]; unsigned __int64
0x18001ee0b  mov     rcx, [r14]
0x18001ee0e  mov     r8, [rax+88h]
0x18001ee15  mov     rcx, [rcx+r15*8]; unsigned __int16 *
0x18001ee19  mov     r8, [r8+r12*8]; unsigned __int16 *
0x18001ee1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ee22  mov     ebx, eax
0x18001ee24  test    eax, eax
0x18001ee26  jns     loc_18001EEC8
0x18001ee2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee33  lea     rax, WPP_GLOBAL_Control
0x18001ee3a  cmp     rcx, rax
0x18001ee3d  jz      short loc_18001EE63
0x18001ee3f  test    byte ptr [rcx+1Ch], 80h
0x18001ee43  jz      short loc_18001EE63
0x18001ee45  cmp     byte ptr [rcx+19h], 2
0x18001ee49  jb      short loc_18001EE63
0x18001ee4b  mov     rcx, [rcx+10h]
0x18001ee4f  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001ee56  mov     edx, 15h
0x18001ee5b  mov     r9d, ebx
0x18001ee5e  call    WPP_SF_D
0x18001ee63  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ee6a  mov     [rbp+var_40], r13b
0x18001ee6e  mov     [rbp+var_38], rax
0x18001ee72  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ee79  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ee80  mov     [rbp+var_30], r13
0x18001ee84  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001ee88  mov     [rbp+pExceptionObject], rax
0x18001ee8c  mov     [rbp+var_28], r13
0x18001ee90  mov     [rbp+var_20], ebx
0x18001ee93  mov     [rbp+var_1C], 0FFFFFFFFh
0x18001ee9a  mov     [rbp+var_18], 1A4h
0x18001eea1  call    _CxxThrowException_0
0x18001eea7  mov     rcx, [r14]
0x18001eeaa  lea     rdx, [rbp+arg_8]
0x18001eeae  mov     word ptr [rbp+arg_8], r13w
0x18001eeb3  mov     rax, [rcx+r15*8]
0x18001eeb7  mov     [rcx+r15*8+8], rax
0x18001eebc  mov     rax, [r14]
0x18001eebf  lea     rcx, [rax+r15*8]
0x18001eec3  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001eec8  inc     edi
0x18001eeca  jmp     loc_18001EDBA
0x18001eecf  mov     al, 1
0x18001eed1  jmp     short loc_18001EED5
0x18001eed3  xor     al, al
0x18001eed5  add     rsp, 68h
0x18001eed9  pop     r15
0x18001eedb  pop     r14
0x18001eedd  pop     r13
0x18001eedf  pop     r12
0x18001eee1  pop     rdi
0x18001eee2  pop     rsi
0x18001eee3  pop     rbx
0x18001eee4  pop     rbp
0x18001eee5  retn
```
