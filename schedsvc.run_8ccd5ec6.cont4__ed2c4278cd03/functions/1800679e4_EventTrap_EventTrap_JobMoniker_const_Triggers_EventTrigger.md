# EventTrap::EventTrap(JobMoniker const &,Triggers::EventTrigger *)

- ea: `0x1800679e4`
- end: `0x180067cd3`
- name: `??0EventTrap@@QEAA@AEBVJobMoniker@@PEAUEventTrigger@Triggers@@@Z`
- size: `751`
- prototype: `EventTrap *__fastcall(EventTrap *__hidden this, const struct JobMoniker *, struct Triggers::EventTrigger *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800687d0`

## callees

- `0x18000cc40`
- `0x180016f40`
- `0x180027910`
- `0x1800301f0`
- `0x180032c30`
- `0x1800404e0`
- `0x180051258`
- `0x180054c48`
- `0x18005a2bc`
- `0x1800679e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067c61`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180067b20`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180067c39`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180067b20`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x180067c39`

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
      v33 = &qword_1800A8718;
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
      v33 = &qword_1800A8718;
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
      v33 = &qword_1800A8718;
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
0x1800679e4  mov     [rsp-38h+arg_8], rbx
0x1800679e9  mov     [rsp-38h+arg_0], rcx
0x1800679ee  push    rbp
0x1800679ef  push    rsi
0x1800679f0  push    rdi
0x1800679f1  push    r12
0x1800679f3  push    r13
0x1800679f5  push    r14
0x1800679f7  push    r15
0x1800679f9  mov     rbp, rsp
0x1800679fc  sub     rsp, 60h
0x180067a00  mov     rbx, r8
0x180067a03  mov     r14, rcx
0x180067a06  add     rcx, 8; this
0x180067a0a  call    ??0JobMoniker@@QEAA@AEBV0@@Z; JobMoniker::JobMoniker(JobMoniker const &)
0x180067a0f  nop
0x180067a10  mov     [r14+30h], rbx
0x180067a14  lea     r15, [r14+40h]
0x180067a18  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067a1c  mov     [r15], rdi
0x180067a1f  lea     r12, [r14+48h]
0x180067a23  mov     [r12], rdi
0x180067a27  lea     ecx, [rdi+19h]; dwBytes
0x180067a2a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067a2f  mov     rsi, rax
0x180067a32  mov     [rbp+ValuePaths], rax
0x180067a36  xor     r13d, r13d
0x180067a39  test    rax, rax
0x180067a3c  jz      short loc_180067A63
0x180067a3e  mov     rax, [r14+30h]
0x180067a42  mov     edi, [rax+60h]
0x180067a45  mov     ebx, [rax+64h]
0x180067a48  mov     [rsi], r13
0x180067a4b  mov     [rsi+8], r13
0x180067a4f  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBVUser@@PEAULogonJob@@@std@@V?$allocator@U?$pair@$$CBVUser@@PEAULogonJob@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVUser@@PEAULogonJob@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<User const,LogonJob *>>>::_Buyheadnode(void)
0x180067a54  mov     [rsi], rax
0x180067a57  mov     [rsi+10h], ebx
0x180067a5a  mov     [rsi+14h], edi
0x180067a5d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067a61  jmp     short loc_180067A66
0x180067a63  mov     rsi, r13
0x180067a66  mov     [r14+38h], rsi
0x180067a6a  mov     rcx, r15; this
0x180067a6d  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x180067a72  mov     [r15], rdi
0x180067a75  mov     rcx, r12; this
0x180067a78  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x180067a7d  mov     [r12], rdi
0x180067a81  mov     rcx, [r14+30h]
0x180067a85  add     rcx, 68h ; 'h'; this
0x180067a89  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180067a8e  test    eax, eax
0x180067a90  jz      loc_180067BA0
0x180067a96  lea     ebx, [rax+1]
0x180067a99  mov     eax, 2
0x180067a9e  mul     rbx
0x180067aa1  cmovb   rax, rdi
0x180067aa5  mov     rcx, rax; dwBytes
0x180067aa8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067aad  mov     [rbp+ValuePaths], rax
0x180067ab1  mov     rcx, [r14+30h]
0x180067ab5  mov     r8, [rcx+68h]
0x180067ab9  test    r8, r8
0x180067abc  jz      short loc_180067AC3
0x180067abe  mov     r8, [r8]
0x180067ac1  jmp     short loc_180067AC6
0x180067ac3  mov     r8, r13; unsigned __int16 *
0x180067ac6  mov     rdx, rbx; unsigned __int64
0x180067ac9  mov     rcx, rax; unsigned __int16 *
0x180067acc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180067ad1  test    eax, eax
0x180067ad3  jns     short loc_180067B15
0x180067ad5  mov     [rbp+var_38], r13b
0x180067ad9  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180067ae0  mov     [rbp+pExceptionObject], rcx
0x180067ae4  lea     rcx, qword_1800A8718
0x180067aeb  mov     [rbp+var_30], rcx
0x180067aef  mov     [rbp+var_28], r13
0x180067af3  mov     [rbp+var_20], r13
0x180067af7  mov     [rbp+var_18], eax
0x180067afa  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180067b01  mov     dword ptr [rbp+var_14+4], edi
0x180067b04  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180067b0b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180067b0f  call    _CxxThrowException_0
0x180067b15  xor     r8d, r8d; Flags
0x180067b18  lea     rdx, [rbp+ValuePaths]; ValuePaths
0x180067b1c  lea     ecx, [r8+1]; ValuePathsCount
0x180067b20  call    cs:__imp_EvtCreateRenderContext
0x180067b27  nop     dword ptr [rax+rax+00h]
0x180067b2c  mov     rbx, rax
0x180067b2f  mov     rcx, r15; this
0x180067b32  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x180067b37  mov     [r15], rbx
0x180067b3a  test    rbx, rbx
0x180067b3d  jnz     short loc_180067B97
0x180067b3f  call    cs:__imp_GetLastError
0x180067b46  nop     dword ptr [rax+rax+00h]
0x180067b4b  test    eax, eax
0x180067b4d  jle     short loc_180067B57
0x180067b4f  movzx   eax, ax
0x180067b52  or      eax, 80070000h
0x180067b57  mov     [rbp+var_38], r13b
0x180067b5b  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180067b62  mov     [rbp+pExceptionObject], rcx
0x180067b66  lea     rcx, qword_1800A8718
0x180067b6d  mov     [rbp+var_30], rcx
0x180067b71  mov     [rbp+var_28], r13
0x180067b75  mov     [rbp+var_20], r13
0x180067b79  mov     [rbp+var_18], eax
0x180067b7c  mov     dword ptr [rbp+var_14], 0FFFFFFFFh
0x180067b83  mov     dword ptr [rbp+var_14+4], edi
0x180067b86  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180067b8d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180067b91  call    _CxxThrowException_0
0x180067b97  mov     rcx, [rbp+ValuePaths]; void *
0x180067b9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180067ba0  mov     rax, [r14+30h]
0x180067ba4  mov     rcx, [rax+78h]
0x180067ba8  test    rcx, rcx
0x180067bab  jz      loc_180067CB7
0x180067bb1  mov     eax, 8
0x180067bb6  mul     rcx
0x180067bb9  cmovb   rax, rdi
0x180067bbd  mov     rcx, rax; dwBytes
0x180067bc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180067bc5  mov     rdi, rax
0x180067bc8  mov     r8d, r13d
0x180067bcb  mov     rcx, [r14+30h]
0x180067bcf  mov     rax, [rcx+70h]
0x180067bd3  mov     rax, [rax]
0x180067bd6  mov     rcx, [r14+30h]
0x180067bda  cmp     rax, [rcx+70h]
0x180067bde  jz      short loc_180067C30
0x180067be0  mov     rcx, [rax+28h]
0x180067be4  test    rcx, rcx
0x180067be7  jz      short loc_180067BEE
0x180067be9  mov     rdx, [rcx]
0x180067bec  jmp     short loc_180067BF1
0x180067bee  mov     rdx, r13
0x180067bf1  mov     ecx, r8d
0x180067bf4  mov     [rdi+rcx*8], rdx
0x180067bf8  inc     r8d
0x180067bfb  cmp     [rax+19h], r13b
0x180067bff  jnz     short loc_180067BD6
0x180067c01  mov     rcx, [rax+10h]
0x180067c05  cmp     [rcx+19h], r13b
0x180067c09  jnz     short loc_180067C12
0x180067c0b  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAV?$list@U_FILETIME@@V?$allocator@U_FILETIME@@@std@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,std::list<_FILETIME> *>>>::_Min(std::_Tree_node<std::pair<_bstr_t const,std::list<_FILETIME> *>,void *> *)
0x180067c10  jmp     short loc_180067BD6
0x180067c12  mov     rcx, [rax+8]
0x180067c16  jmp     short loc_180067C25
0x180067c18  cmp     rax, [rcx+10h]
0x180067c1c  jnz     short loc_180067C2B
0x180067c1e  mov     rax, rcx
0x180067c21  mov     rcx, [rcx+8]
0x180067c25  cmp     [rcx+19h], r13b
0x180067c29  jz      short loc_180067C18
0x180067c2b  mov     rax, rcx
0x180067c2e  jmp     short loc_180067BD6
0x180067c30  xor     r8d, r8d; Flags
0x180067c33  mov     rdx, rdi; ValuePaths
0x180067c36  mov     ecx, [rcx+78h]; ValuePathsCount
0x180067c39  call    cs:__imp_EvtCreateRenderContext
0x180067c40  nop     dword ptr [rax+rax+00h]
0x180067c45  mov     rbx, rax
0x180067c48  mov     rcx, r12; this
0x180067c4b  call    ?Close@AutoEvtHandle@@QEAAXXZ; AutoEvtHandle::Close(void)
0x180067c50  mov     [r12], rbx
0x180067c54  mov     rcx, rdi; void *
0x180067c57  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180067c5c  test    rbx, rbx
0x180067c5f  jnz     short loc_180067CB7
0x180067c61  call    cs:__imp_GetLastError
0x180067c68  nop     dword ptr [rax+rax+00h]
0x180067c6d  test    eax, eax
0x180067c6f  jle     short loc_180067C79
0x180067c71  movzx   eax, ax
0x180067c74  or      eax, 80070000h
0x180067c79  mov     [rbp+var_38], r13b
0x180067c7d  lea     rcx, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x180067c84  mov     [rbp+pExceptionObject], rcx
0x180067c88  lea     rcx, qword_1800A8718
0x180067c8f  mov     [rbp+var_30], rcx
0x180067c93  mov     [rbp+var_28], r13
0x180067c97  mov     [rbp+var_20], r13
0x180067c9b  mov     [rbp+var_18], eax
0x180067c9e  mov     [rbp+var_14], 0FFFFFFFFFFFFFFFFh
0x180067ca6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x180067cad  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180067cb1  call    _CxxThrowException_0
0x180067cb7  mov     rax, r14
0x180067cba  mov     rbx, [rsp+60h+arg_8]
0x180067cc2  add     rsp, 60h
0x180067cc6  pop     r15
0x180067cc8  pop     r14
0x180067cca  pop     r13
0x180067ccc  pop     r12
0x180067cce  pop     rdi
0x180067ccf  pop     rsi
0x180067cd0  pop     rbp
0x180067cd1  retn
```
