# ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,std::vector<bool,std::allocator<bool>> &)

- ea: `0x18001eeec`
- end: `0x18001eff9`
- name: `?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAV?$vector@_NV?$allocator@_N@std@@@std@@@Z`
- size: `269`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001df44`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x180003d48`
- `0x1800154f4`
- `0x18001eeec`
- `0x18001f908`

## string_xrefs

- `0x18001ef58`: `admin\wmi\events\forwarding\collector\common\subdata.cpp`

## pseudocode

```c
char __fastcall ReadMetadataProp(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  unsigned int v6; // ebp
  __int64 v7; // rax
  bool v8; // bl
  __int64 v9; // rax
  __int64 v10; // rdx
  _BYTE v12[16]; // [rsp+20h] [rbp-78h] BYREF
  void **pExceptionObject; // [rsp+30h] [rbp-68h] BYREF
  char v14; // [rsp+38h] [rbp-60h]
  const char *v15; // [rsp+40h] [rbp-58h]
  __int64 v16; // [rsp+48h] [rbp-50h]
  __int64 v17; // [rsp+50h] [rbp-48h]
  int v18; // [rsp+58h] [rbp-40h]
  int v19; // [rsp+5Ch] [rbp-3Ch]
  int v20; // [rsp+60h] [rbp-38h]

  if ( *(_DWORD *)a1 <= 3u )
    return 0;
  _mm_lfence();
  v5 = *(_QWORD *)(a1 + 8);
  v6 = 0;
  if ( !*(_DWORD *)(v5 + 72) )
    return 0;
  if ( *(_DWORD *)(v5 + 72) != 5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids, 87);
    }
    v14 = 0;
    v15 = "admin\\wmi\\events\\forwarding\\collector\\common\\subdata.cpp";
    v16 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v17 = 0;
    v18 = 87;
    v19 = -1;
    v20 = 329;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  std::vector<bool>::resize(a3, *(unsigned int *)(v5 + 80));
  v7 = *(_QWORD *)(a1 + 8);
  if ( *(_DWORD *)(v7 + 80) )
  {
    do
    {
      v8 = *(_BYTE *)(v6 + *(_QWORD *)(v7 + 88)) == 1;
      v9 = std::vector<bool>::operator[](a3, v12, v6);
      LOBYTE(v10) = v8;
      std::_Vb_reference<std::_Wrap_alloc<std::allocator<unsigned int>>>::operator=(v9, v10);
      v7 = *(_QWORD *)(a1 + 8);
      ++v6;
    }
    while ( v6 < *(_DWORD *)(v7 + 80) );
  }
  return 1;
}

```

## disassembly

```asm
0x18001eeec  push    rbx
0x18001eeee  push    rbp
0x18001eeef  push    rsi
0x18001eef0  push    rdi
0x18001eef1  sub     rsp, 78h
0x18001eef5  cmp     dword ptr [rcx], 3
0x18001eef8  mov     rsi, r8
0x18001eefb  mov     rdi, rcx
0x18001eefe  jbe     loc_18001EFEE
0x18001ef04  lfence
0x18001ef07  mov     rax, [rcx+8]
0x18001ef0b  xor     ebp, ebp
0x18001ef0d  cmp     [rax+48h], ebp
0x18001ef10  jz      loc_18001EFEE
0x18001ef16  cmp     dword ptr [rax+48h], 5
0x18001ef1a  jz      loc_18001EFA5
0x18001ef20  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef27  lea     rax, WPP_GLOBAL_Control
0x18001ef2e  lea     ebx, [rbp+57h]
0x18001ef31  cmp     rcx, rax
0x18001ef34  jz      short loc_18001EF58
0x18001ef36  test    byte ptr [rcx+1Ch], 80h
0x18001ef3a  jz      short loc_18001EF58
0x18001ef3c  cmp     byte ptr [rcx+19h], 2
0x18001ef40  jb      short loc_18001EF58
0x18001ef42  mov     rcx, [rcx+10h]
0x18001ef46  lea     edx, [rbp+11h]
0x18001ef49  mov     r9d, ebx
0x18001ef4c  lea     r8, WPP_1484ca0113be328fb1dd317c070a3401_Traceguids
0x18001ef53  call    WPP_SF_D
0x18001ef58  lea     rax, aAdminWmiEvents_4; "admin\\wmi\\events\\forwarding\\collect"...
0x18001ef5f  mov     [rsp+98h+var_60], bpl
0x18001ef64  mov     [rsp+98h+var_58], rax
0x18001ef69  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001ef70  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001ef77  mov     [rsp+98h+var_50], rbp
0x18001ef7c  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001ef81  mov     [rsp+98h+pExceptionObject], rax
0x18001ef86  mov     [rsp+98h+var_48], rbp
0x18001ef8b  mov     [rsp+98h+var_40], ebx
0x18001ef8f  mov     [rsp+98h+var_3C], 0FFFFFFFFh
0x18001ef97  mov     [rsp+98h+var_38], 149h
0x18001ef9f  call    _CxxThrowException_0
0x18001efa5  mov     edx, [rax+50h]
0x18001efa8  mov     rcx, rsi
0x18001efab  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x18001efb0  mov     rax, [rdi+8]
0x18001efb4  cmp     [rax+50h], ebp
0x18001efb7  jbe     short loc_18001EFEA
0x18001efb9  mov     rax, [rax+58h]
0x18001efbd  lea     rdx, [rsp+98h+var_78]
0x18001efc2  mov     r8d, ebp
0x18001efc5  mov     rcx, rsi
0x18001efc8  cmp     byte ptr [r8+rax], 1
0x18001efcd  setz    bl
0x18001efd0  call    ??A?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@1@_K@Z; std::vector<bool>::operator[](unsigned __int64)
0x18001efd5  mov     rcx, rax
0x18001efd8  mov     dl, bl
0x18001efda  call    ??4?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@std@@QEAAAEAV01@_N@Z; std::_Vb_reference<std::_Wrap_alloc<std::allocator<uint>>>::operator=(bool)
0x18001efdf  mov     rax, [rdi+8]
0x18001efe3  inc     ebp
0x18001efe5  cmp     ebp, [rax+50h]
0x18001efe8  jb      short loc_18001EFB9
0x18001efea  mov     al, 1
0x18001efec  jmp     short loc_18001EFF0
0x18001efee  xor     al, al
0x18001eff0  add     rsp, 78h
0x18001eff4  pop     rdi
0x18001eff5  pop     rsi
0x18001eff6  pop     rbp
0x18001eff7  pop     rbx
0x18001eff8  retn
```
