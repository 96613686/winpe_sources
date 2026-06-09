# EventTrap::EventTrap(JobMoniker const &,Triggers::EventTrigger *)

- ea: `0x180064934`
- end: `0x180064c0a`
- name: `??0EventTrap@@QEAA@AEBVJobMoniker@@PEAUEventTrigger@Triggers@@@Z`
- size: `726`
- prototype: `EventTrap *__fastcall(EventTrap *__hidden this, const struct JobMoniker *, struct Triggers::EventTrigger *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180065680`

## callees

- `0x180019130`
- `0x18001a260`
- `0x18002a9e0`
- `0x180030f80`
- `0x180030ff4`
- `0x18003cec0`
- `0x18004eee4`
- `0x180052554`
- `0x18005790c`
- `0x180064934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b9f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180064a70`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180064b7d`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180064a70`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180064b7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
EventTrap *__fastcall EventTrap::EventTrap(
        EventTrap *this,
        const struct JobMoniker *a2,
        struct Triggers::EventTrigger *a3)
{
  _QWORD *v5; // r15
  _QWORD *v6; // r12
  WCHAR *v7; // rsi
  __int64 v8; // rax
  int v9; // edi
  int v10; // ebx
  unsigned int v11; // eax
  unsigned __int64 v12; // rbx
  WCHAR *v13; // rax
  const unsigned __int16 **v14; // r8
  const unsigned __int16 *v15; // r8
  int v16; // eax
  EVT_HANDLE v17; // rbx
  signed int LastError; // eax
  unsigned __int64 v19; // rcx
  LPCWSTR *v20; // rdi
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rcx
  const WCHAR **v24; // rcx
  const WCHAR *v25; // rdx
  __int64 v26; // rcx
  __int64 i; // rcx
  EVT_HANDLE RenderContext; // rbx
  signed int v29; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-40h] BYREF
  char v32; // [rsp+28h] [rbp-38h]
  const unsigned __int16 *v33; // [rsp+30h] [rbp-30h]
  __int64 v34; // [rsp+38h] [rbp-28h]
  __int64 v35; // [rsp+40h] [rbp-20h]
  int v36; // [rsp+48h] [rbp-18h]
  __int64 v37; // [rsp+4Ch] [rbp-14h]
  LPCWSTR ValuePaths; // [rsp+B0h] [rbp+50h] BYREF

  JobMoniker::JobMoniker((EventTrap *)((char *)this + 8), a2);
  *((_QWORD *)this + 6) = a3;
  v5 = (_QWORD *)((char *)this + 64);
  *((_QWORD *)this + 8) = -1;
  v6 = (_QWORD *)((char *)this + 72);
  *((_QWORD *)this + 9) = -1;
  v7 = (WCHAR *)operator new(0x18u);
  ValuePaths = v7;
  if ( v7 )
  {
    v8 = *((_QWORD *)this + 6);
    v9 = *(_DWORD *)(v8 + 96);
    v10 = *(_DWORD *)(v8 + 100);
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 1) = 0;
    *(_QWORD *)v7 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<User const,LogonJob *>>>::_Buyheadnode();
    *((_DWORD *)v7 + 4) = v10;
    *((_DWORD *)v7 + 5) = v9;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 7) = v7;
  AutoEvtHandle::Close((EventTrap *)((char *)this + 64));
  *v5 = -1;
  AutoEvtHandle::Close((EventTrap *)((char *)this + 72));
  *v6 = -1;
  v11 = _bstr_t::length((_bstr_t *)(*((_QWORD *)this + 6) + 104LL));
  if ( v11 )
  {
    v12 = v11 + 1;
    v13 = (WCHAR *)operator new(saturated_mul(v12, 2u));
    ValuePaths = v13;
    v14 = *(const unsigned __int16 ***)(*((_QWORD *)this + 6) + 104LL);
    if ( v14 )
      v15 = *v14;
    else
      v15 = 0;
    v16 = StringCchCopyW(v13, v12, v15);
    if ( v16 < 0 )
    {
      v32 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v33 = &qword_1800A4718;
      v34 = 0;
      v35 = 0;
      v36 = v16;
      v37 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    v17 = EvtCreateRenderContext(1u, &ValuePaths, 0);
    AutoEvtHandle::Close((EventTrap *)((char *)this + 64));
    *v5 = v17;
    if ( !v17 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v32 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v33 = &qword_1800A4718;
      v34 = 0;
      v35 = 0;
      v36 = LastError;
      v37 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    operator delete((void *)ValuePaths);
  }
  v19 = *(_QWORD *)(*((_QWORD *)this + 6) + 120LL);
  if ( v19 )
  {
    v20 = (LPCWSTR *)operator new(saturated_mul(v19, 8u));
    LODWORD(v21) = 0;
    v22 = **(_QWORD **)(*((_QWORD *)this + 6) + 112LL);
    while ( 1 )
    {
      v23 = *((_QWORD *)this + 6);
      if ( v22 == *(_QWORD *)(v23 + 112) )
        break;
      v24 = *(const WCHAR ***)(v22 + 40);
      if ( v24 )
        v25 = *v24;
      else
        v25 = 0;
      v20[(unsigned int)v21] = v25;
      v21 = (unsigned int)(v21 + 1);
      if ( !*(_BYTE *)(v22 + 25) )
      {
        v26 = *(_QWORD *)(v22 + 16);
        if ( *(_BYTE *)(v26 + 25) )
        {
          for ( i = *(_QWORD *)(v22 + 8); !*(_BYTE *)(i + 25) && v22 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v22 = i;
          v22 = i;
        }
        else
        {
          v22 = std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(
                  v26,
                  v25,
                  v21);
        }
      }
    }
    RenderContext = EvtCreateRenderContext(*(_DWORD *)(v23 + 120), v20, 0);
    AutoEvtHandle::Close((EventTrap *)((char *)this + 72));
    *v6 = RenderContext;
    operator delete(v20);
    if ( !RenderContext )
    {
      v29 = GetLastError();
      if ( v29 > 0 )
        v29 = (unsigned __int16)v29 | 0x80070000;
      v32 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v33 = &qword_1800A4718;
      v34 = 0;
      v35 = 0;
      v36 = v29;
      v37 = -1;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180064934  mov     [rsp-38h+arg_8], rbx
0x180064939  mov     [rsp-38h+arg_0], rcx
0x18006493e  push    rbp
0x18006493f  push    rsi
0x180064940  push    rdi
0x180064941  push    r12
0x180064943  push    r13
0x180064945  push    r14
0x180064947  push    r15
0x180064949  mov     rbp, rsp
0x18006494c  sub     rsp, 60h
0x180064950  mov     rbx, r8
0x180064953  mov     r14, rcx
0x180064956  add     rcx, 8; this
0x18006495a  call    ??0JobMoniker@@QEAA@AEBV0@@Z; JobMoniker::JobMoniker(JobMoniker const &)
0x18006495f  nop
0x180064960  mov     [r14+30h], rbx
0x180064964  lea     r15, [r14+40h]
0x180064968  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006496c  mov     [r15], rdi
0x18006496f  lea     r12, [r14+48h]
0x180064973  mov     [r12], rdi
0x180064977  lea     ecx, [rdi+19h]; dwBytes
0x18006497a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006497f  mov     rsi, rax
0x180064982  mov     [rbp+ValuePaths], rax
0x180064986  xor     r13d, r13d
0x180064989  test    rax, rax
0x18006498c  jz      short loc_1800649B3
0x18006498e  mov     rax, [r14+30h]
0x180064992  mov     edi, [rax+60h]
0x180064995  mov     ebx, [rax+64h]
0x180064998  mov     [rsi], r13
0x18006499b  mov     [rsi+8], r13
0x18006499f  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBVUser@@PEAULogonJob@@@std@@V?$allocator@U?$pair@$$CBVUser@@PEAULogonJob@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVUser@@PEAULogonJob@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<User const,LogonJob *>>>::_Buyheadnode(void)
0x1800649a4  mov     [rsi], rax
0x1800649a7  mov     [rsi+10h], ebx
0x1800649aa  mov     [rsi+14h], edi
0x1800649ad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800649b1  jmp     short loc_1800649B6
0x1800649b3  mov     rsi, r13
0x1800649b6  mov     [r14+38h], rsi
0x1800649ba  mov     rcx, r15; this
0x1800649bd  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x1800649c2  mov     [r15], rdi
0x1800649c5  mov     rcx, r12; this
0x1800649c8  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x1800649cd  mov     [r12], rdi
0x1800649d1  mov     rcx, [r14+30h]
0x1800649d5  add     rcx, 68h ; 'h'; this
0x1800649d9  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x1800649de  test    eax, eax
0x1800649e0  jz      loc_180064AE4
0x1800649e6  lea     ebx, [rax+1]
0x1800649e9  mov     eax, 2
0x1800649ee  mul     rbx
0x1800649f1  cmovb   rax, rdi
0x1800649f5  mov     rcx, rax; dwBytes
0x1800649f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800649fd  mov     [rbp+ValuePaths], rax
0x180064a01  mov     rcx, [r14+30h]
0x180064a05  mov     r8, [rcx+68h]
0x180064a09  test    r8, r8
0x180064a0c  jz      short loc_180064A13
0x180064a0e  mov     r8, [r8]
0x180064a11  jmp     short loc_180064A16
0x180064a13  mov     r8, r13; unsigned __int16 *
0x180064a16  mov     rdx, rbx; unsigned __int64
0x180064a19  mov     rcx, rax; unsigned __int16 *
0x180064a1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064a21  test    eax, eax
0x180064a23  jns     short loc_180064A65
0x180064a25  mov     [rbp+var_38], r13b
0x180064a29  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180064a30  mov     [rbp+pExceptionObject], rcx
0x180064a34  lea     rcx, qword_1800A4718
0x180064a3b  mov     [rbp+var_30], rcx
0x180064a3f  mov     [rbp+var_28], r13
0x180064a43  mov     [rbp+var_20], r13
0x180064a47  mov     [rbp+var_18], eax
0x180064a4a  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180064a51  mov     dword ptr [rbp+var_14+4], edi
0x180064a54  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180064a5b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180064a5f  call    _CxxThrowException_0
0x180064a65  xor     r8d, r8d; Flags
0x180064a68  lea     rdx, [rbp+ValuePaths]; ValuePaths
0x180064a6c  lea     ecx, [r8+1]; ValuePathsCount
0x180064a70  call    cs:__imp_EvtCreateRenderContext
0x180064a76  mov     rbx, rax
0x180064a79  mov     rcx, r15; this
0x180064a7c  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x180064a81  mov     [r15], rbx
0x180064a84  test    rbx, rbx
0x180064a87  jnz     short loc_180064ADB
0x180064a89  call    cs:__imp_GetLastError
0x180064a8f  test    eax, eax
0x180064a91  jle     short loc_180064A9B
0x180064a93  movzx   eax, ax
0x180064a96  or      eax, 80070000h
0x180064a9b  mov     [rbp+var_38], r13b
0x180064a9f  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180064aa6  mov     [rbp+pExceptionObject], rcx
0x180064aaa  lea     rcx, qword_1800A4718
0x180064ab1  mov     [rbp+var_30], rcx
0x180064ab5  mov     [rbp+var_28], r13
0x180064ab9  mov     [rbp+var_20], r13
0x180064abd  mov     [rbp+var_18], eax
0x180064ac0  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180064ac7  mov     dword ptr [rbp+var_14+4], edi
0x180064aca  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180064ad1  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180064ad5  call    _CxxThrowException_0
0x180064adb  mov     rcx, [rbp+ValuePaths]; void *
0x180064adf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180064ae4  mov     rax, [r14+30h]
0x180064ae8  mov     rcx, [rax+78h]
0x180064aec  test    rcx, rcx
0x180064aef  jz      loc_180064BEF
0x180064af5  mov     eax, 8
0x180064afa  mul     rcx
0x180064afd  cmovb   rax, rdi
0x180064b01  mov     rcx, rax; dwBytes
0x180064b04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064b09  mov     rdi, rax
0x180064b0c  mov     r8d, r13d
0x180064b0f  mov     rcx, [r14+30h]
0x180064b13  mov     rax, [rcx+70h]
0x180064b17  mov     rax, [rax]
0x180064b1a  mov     rcx, [r14+30h]
0x180064b1e  cmp     rax, [rcx+70h]
0x180064b22  jz      short loc_180064B74
0x180064b24  mov     rcx, [rax+28h]
0x180064b28  test    rcx, rcx
0x180064b2b  jz      short loc_180064B32
0x180064b2d  mov     rdx, [rcx]
0x180064b30  jmp     short loc_180064B35
0x180064b32  mov     rdx, r13
0x180064b35  mov     ecx, r8d
0x180064b38  mov     [rdi+rcx*8], rdx
0x180064b3c  inc     r8d
0x180064b3f  cmp     [rax+19h], r13b
0x180064b43  jnz     short loc_180064B1A
0x180064b45  mov     rcx, [rax+10h]
0x180064b49  cmp     [rcx+19h], r13b
0x180064b4d  jnz     short loc_180064B56
0x180064b4f  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(std::_Tree_node<std::pair<_bstr_t const,std::list<_FILETIME> *>,void *> *)
0x180064b54  jmp     short loc_180064B1A
0x180064b56  mov     rcx, [rax+8]
0x180064b5a  jmp     short loc_180064B69
0x180064b5c  cmp     rax, [rcx+10h]
0x180064b60  jnz     short loc_180064B6F
0x180064b62  mov     rax, rcx
0x180064b65  mov     rcx, [rcx+8]
0x180064b69  cmp     [rcx+19h], r13b
0x180064b6d  jz      short loc_180064B5C
0x180064b6f  mov     rax, rcx
0x180064b72  jmp     short loc_180064B1A
0x180064b74  xor     r8d, r8d; Flags
0x180064b77  mov     rdx, rdi; ValuePaths
0x180064b7a  mov     ecx, [rcx+78h]; ValuePathsCount
0x180064b7d  call    cs:__imp_EvtCreateRenderContext
0x180064b83  mov     rbx, rax
0x180064b86  mov     rcx, r12; this
0x180064b89  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x180064b8e  mov     [r12], rbx
0x180064b92  mov     rcx, rdi; void *
0x180064b95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180064b9a  test    rbx, rbx
0x180064b9d  jnz     short loc_180064BEF
0x180064b9f  call    cs:__imp_GetLastError
0x180064ba5  test    eax, eax
0x180064ba7  jle     short loc_180064BB1
0x180064ba9  movzx   eax, ax
0x180064bac  or      eax, 80070000h
0x180064bb1  mov     [rbp+var_38], r13b
0x180064bb5  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180064bbc  mov     [rbp+pExceptionObject], rcx
0x180064bc0  lea     rcx, qword_1800A4718
0x180064bc7  mov     [rbp+var_30], rcx
0x180064bcb  mov     [rbp+var_28], r13
0x180064bcf  mov     [rbp+var_20], r13
0x180064bd3  mov     [rbp+var_18], eax
0x180064bd6  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180064bde  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180064be5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180064be9  call    _CxxThrowException_0
0x180064bef  mov     rax, r14
0x180064bf2  mov     rbx, [rsp+60h+arg_8]
0x180064bfa  add     rsp, 60h
0x180064bfe  pop     r15
0x180064c00  pop     r14
0x180064c02  pop     r13
0x180064c04  pop     r12
0x180064c06  pop     rdi
0x180064c07  pop     rsi
0x180064c08  pop     rbp
0x180064c09  retn
```
