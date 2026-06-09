# CopyFromCom(IWdsMetadata *,CWdsMetadata *)

- ea: `0x18000c4cc`
- end: `0x18000c62d`
- name: `?CopyFromCom@@YAKPEAUIWdsMetadata@@PEAVCWdsMetadata@@@Z`
- size: `353`
- prototype: `unsigned int(struct IWdsMetadata *, struct CWdsMetadata *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800055b0`
- `0x180006320`
- `0x180006598`
- `0x1800068d0`

## callees

- `0x180009194`
- `0x18000c4cc`
- `0x18000c634`
- `0x18000c730`
- `0x18000d010`

## import_xrefs

- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c5d8`
- `WdsCommonLib!?WIN32_FROM_HRESULT@@YAKJ@Z` at `0x18000c5d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c59a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c5f6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c59a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c5f6`

## pseudocode

```c
__int64 __fastcall CopyFromCom(struct IWdsMetadata *a1, struct CWdsMetadata *a2)
{
  __int64 v2; // rax
  unsigned int appended; // ebx
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // ecx
  unsigned int v10; // edi
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int v18; // [rsp+50h] [rbp+30h] BYREF
  __int64 v19; // [rsp+60h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+48h] BYREF

  v2 = *(_QWORD *)a1;
  appended = 0;
  v19 = 0;
  bstrString = 0;
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IWdsMetadata *, unsigned int *))(v2 + 24))(a1, &v18);
  if ( (int)ElValidateHr_2(v6, v7, v8, 0x95u) < 0 )
  {
    v9 = v6;
LABEL_14:
    appended = WIN32_FROM_HRESULT(v9);
    goto LABEL_15;
  }
  v10 = 0;
  if ( v18 )
  {
    while ( 1 )
    {
      v11 = (*(__int64 (__fastcall **)(struct IWdsMetadata *, _QWORD, __int64 *))(*(_QWORD *)a1 + 32LL))(a1, v10, &v19);
      if ( (int)ElValidateHr_2(v11, v12, v13, 0x9Au) < 0 )
        break;
      v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v19 + 120LL))(v19, &bstrString);
      if ( (int)ElValidateHr_2(v11, v14, v15, 0x9Du) < 0 )
        break;
      appended = CWdsMetadata::AppendEntry(a2, bstrString);
      if ( (unsigned int)ElValidateWin32_3(appended) )
        goto LABEL_15;
      if ( bstrString )
      {
        SysFreeString(bstrString);
        bstrString = 0;
      }
      v16 = v19;
      if ( v19 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v16 = 0;
        v19 = 0;
      }
      if ( ++v10 >= v18 )
        goto LABEL_16;
    }
    v9 = v11;
    goto LABEL_14;
  }
LABEL_15:
  v16 = v19;
LABEL_16:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    v16 = v19;
    bstrString = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return appended;
}

```

## disassembly

```asm
0x18000c4cc  push    rbp
0x18000c4ce  push    rbx
0x18000c4cf  push    rsi
0x18000c4d0  push    rdi
0x18000c4d1  push    r14
0x18000c4d3  mov     rbp, rsp
0x18000c4d6  sub     rsp, 20h
0x18000c4da  mov     rax, [rcx]
0x18000c4dd  xor     ebx, ebx
0x18000c4df  mov     r14, rdx
0x18000c4e2  mov     [rbp+arg_10], rbx
0x18000c4e6  lea     rdx, [rbp+arg_0]
0x18000c4ea  mov     [rbp+bstrString], rbx
0x18000c4ee  mov     rsi, rcx
0x18000c4f1  mov     [rbp+arg_0], ebx
0x18000c4f4  mov     rax, [rax+18h]
0x18000c4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4fd  mov     r9d, 95h
0x18000c503  mov     ecx, eax
0x18000c505  mov     edi, eax
0x18000c507  call    ElValidateHr_2
0x18000c50c  test    eax, eax
0x18000c50e  jns     short loc_18000C517
0x18000c510  mov     ecx, edi
0x18000c512  jmp     loc_18000C5D8
0x18000c517  xor     edi, edi
0x18000c519  cmp     [rbp+arg_0], ebx
0x18000c51c  jbe     loc_18000C5E6
0x18000c522  mov     rax, [rsi]
0x18000c525  lea     r8, [rbp+arg_10]
0x18000c529  mov     edx, edi
0x18000c52b  mov     rcx, rsi
0x18000c52e  mov     rax, [rax+20h]
0x18000c532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c537  mov     r9d, 9Ah
0x18000c53d  mov     ecx, eax
0x18000c53f  mov     ebx, eax
0x18000c541  call    ElValidateHr_2
0x18000c546  test    eax, eax
0x18000c548  js      loc_18000C5D6
0x18000c54e  mov     rcx, [rbp+arg_10]
0x18000c552  lea     rdx, [rbp+bstrString]
0x18000c556  mov     rax, [rcx]
0x18000c559  mov     rax, [rax+78h]
0x18000c55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c562  mov     r9d, 9Dh
0x18000c568  mov     ecx, eax
0x18000c56a  mov     ebx, eax
0x18000c56c  call    ElValidateHr_2
0x18000c571  test    eax, eax
0x18000c573  js      short loc_18000C5D6
0x18000c575  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x18000c579  mov     rcx, r14; this
0x18000c57c  call    ?AppendEntry@CWdsMetadata@@QEAAKPEBG@Z; CWdsMetadata::AppendEntry(ushort const *)
0x18000c581  mov     ecx, eax
0x18000c583  mov     ebx, eax
0x18000c585  call    ElValidateWin32_3
0x18000c58a  test    eax, eax
0x18000c58c  jnz     short loc_18000C5E6
0x18000c58e  mov     rax, [rbp+bstrString]
0x18000c592  test    rax, rax
0x18000c595  jz      short loc_18000C5AE
0x18000c597  mov     rcx, rax; bstrString
0x18000c59a  call    cs:__imp_SysFreeString
0x18000c5a1  nop     dword ptr [rax+rax+00h]
0x18000c5a6  mov     [rbp+bstrString], 0
0x18000c5ae  mov     rcx, [rbp+arg_10]
0x18000c5b2  test    rcx, rcx
0x18000c5b5  jz      short loc_18000C5C9
0x18000c5b7  mov     rax, [rcx]
0x18000c5ba  mov     rax, [rax+10h]
0x18000c5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5c3  xor     ecx, ecx
0x18000c5c5  mov     [rbp+arg_10], rcx
0x18000c5c9  inc     edi
0x18000c5cb  cmp     edi, [rbp+arg_0]
0x18000c5ce  jb      loc_18000C522
0x18000c5d4  jmp     short loc_18000C5EA
0x18000c5d6  mov     ecx, ebx
0x18000c5d8  call    cs:__imp_?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18000c5df  nop     dword ptr [rax+rax+00h]
0x18000c5e4  mov     ebx, eax
0x18000c5e6  mov     rcx, [rbp+arg_10]
0x18000c5ea  mov     rax, [rbp+bstrString]
0x18000c5ee  test    rax, rax
0x18000c5f1  jz      short loc_18000C60E
0x18000c5f3  mov     rcx, rax; bstrString
0x18000c5f6  call    cs:__imp_SysFreeString
0x18000c5fd  nop     dword ptr [rax+rax+00h]
0x18000c602  mov     rcx, [rbp+arg_10]
0x18000c606  mov     [rbp+bstrString], 0
0x18000c60e  test    rcx, rcx
0x18000c611  jz      short loc_18000C61F
0x18000c613  mov     rax, [rcx]
0x18000c616  mov     rax, [rax+10h]
0x18000c61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c61f  mov     eax, ebx
0x18000c621  add     rsp, 20h
0x18000c625  pop     r14
0x18000c627  pop     rdi
0x18000c628  pop     rsi
0x18000c629  pop     rbx
0x18000c62a  pop     rbp
0x18000c62b  retn
```
