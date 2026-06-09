# CVariant::GetData(void * *,ulong,ulong *)

- ea: `0x18000d528`
- end: `0x18000d609`
- name: `?GetData@CVariant@@QEAAJPEAPEAXKPEAK@Z`
- size: `225`
- prototype: `HRESULT __fastcall(CVariant *this, void **, int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011c18`

## callees

- `0x180008760`
- `0x1800096f0`
- `0x18000d2b8`
- `0x18000d330`
- `0x18000d528`
- `0x180015646`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d590`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5c9`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d57f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d57f`

## pseudocode

```c
HRESULT __fastcall CVariant::GetData(CVariant *this, void **a2, int a3, unsigned int *a4)
{
  unsigned __int16 v8; // dx
  HRESULT result; // eax
  UINT v10; // eax
  void *v11; // rax
  size_t *v12; // r8
  size_t v13; // rdx
  unsigned int v14; // eax
  void *v15; // rax

  if ( a3 == 1 )
  {
    v8 = 8;
  }
  else
  {
    v8 = 3;
    if ( a3 != 4 )
    {
      if ( a3 != 7 )
        goto LABEL_7;
      v8 = 8200;
    }
  }
  result = CVariant::ChangeType(this, v8);
  if ( result )
    return result;
LABEL_7:
  if ( ((a3 - 3) & 0xFFFFFFFB) != 0 )
  {
    if ( a3 == 1 )
    {
      v10 = 2 * SysStringLen(*((BSTR *)this + 2)) + 2;
      *a4 = v10;
      v11 = CoTaskMemAlloc(v10);
      *a2 = v11;
      if ( v11 )
      {
        v13 = (unsigned __int64)*a4 >> 1;
        if ( v13 )
          StringCopyWorkerW((STRSAFE_LPWSTR)v11, v13, v12, *((STRSAFE_PCNZWCH *)this + 2), 0x7FFFFFFEu);
        return 0;
      }
    }
    else
    {
      v14 = iTypeSize(*((_WORD *)this + 4));
      *a4 = v14;
      v15 = CoTaskMemAlloc(v14);
      *a2 = v15;
      if ( v15 )
      {
        memcpy_0(v15, (char *)this + 16, *a4);
        return 0;
      }
    }
    return -2147217402;
  }
  return CVariant::GetArrayData(this, a2, a4);
}

```

## disassembly

```asm
0x18000d528  push    rbx
0x18000d52a  push    rsi
0x18000d52b  push    rdi
0x18000d52c  push    r14
0x18000d52e  sub     rsp, 38h
0x18000d532  mov     eax, r8d
0x18000d535  mov     rdi, r9
0x18000d538  mov     esi, r8d
0x18000d53b  mov     r14, rdx
0x18000d53e  mov     rbx, rcx
0x18000d541  sub     eax, 1
0x18000d544  jz      short loc_18000D55A
0x18000d546  mov     edx, 3
0x18000d54b  sub     eax, edx
0x18000d54d  jz      short loc_18000D55F
0x18000d54f  cmp     eax, edx
0x18000d551  jnz     short loc_18000D56C
0x18000d553  mov     edx, 2008h
0x18000d558  jmp     short loc_18000D55F
0x18000d55a  mov     edx, 8; unsigned __int16
0x18000d55f  call    ?ChangeType@CVariant@@QEAAJG@Z; CVariant::ChangeType(ushort)
0x18000d564  test    eax, eax
0x18000d566  jnz     loc_18000D5FF
0x18000d56c  lea     eax, [rsi-3]
0x18000d56f  test    eax, 0FFFFFFFBh
0x18000d574  jz      short loc_18000D5F1
0x18000d576  cmp     esi, 1
0x18000d579  jnz     short loc_18000D5BC
0x18000d57b  mov     rcx, [rbx+10h]; pbstr
0x18000d57f  call    cs:__imp_SysStringLen
0x18000d585  lea     eax, ds:2[rax*2]
0x18000d58c  mov     ecx, eax; cb
0x18000d58e  mov     [rdi], eax
0x18000d590  call    cs:__imp_CoTaskMemAlloc
0x18000d596  mov     [r14], rax
0x18000d599  test    rax, rax
0x18000d59c  jz      short loc_18000D5D7
0x18000d59e  mov     edx, [rdi]
0x18000d5a0  shr     rdx, 1; cchDest
0x18000d5a3  jz      short loc_18000D5ED
0x18000d5a5  mov     r9, [rbx+10h]; pszSrc
0x18000d5a9  mov     rcx, rax; pszDest
0x18000d5ac  mov     [rsp+58h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000d5b5  call    StringCopyWorkerW
0x18000d5ba  jmp     short loc_18000D5ED
0x18000d5bc  movzx   ecx, word ptr [rbx+8]; unsigned __int16
0x18000d5c0  call    ?iTypeSize@@YAHG@Z; iTypeSize(ushort)
0x18000d5c5  mov     ecx, eax; cb
0x18000d5c7  mov     [rdi], ecx
0x18000d5c9  call    cs:__imp_CoTaskMemAlloc
0x18000d5cf  mov     [r14], rax
0x18000d5d2  test    rax, rax
0x18000d5d5  jnz     short loc_18000D5DE
0x18000d5d7  mov     eax, 80041006h
0x18000d5dc  jmp     short loc_18000D5FF
0x18000d5de  mov     r8d, [rdi]; Size
0x18000d5e1  lea     rdx, [rbx+10h]; Src
0x18000d5e5  mov     rcx, rax; void *
0x18000d5e8  call    memcpy_0
0x18000d5ed  xor     eax, eax
0x18000d5ef  jmp     short loc_18000D5FF
0x18000d5f1  mov     r8, rdi; unsigned int *
0x18000d5f4  mov     rdx, r14; void **
0x18000d5f7  mov     rcx, rbx; this
0x18000d5fa  call    ?GetArrayData@CVariant@@AEAAJPEAPEAXPEAK@Z; CVariant::GetArrayData(void * *,ulong *)
0x18000d5ff  add     rsp, 38h
0x18000d603  pop     r14
0x18000d605  pop     rdi
0x18000d606  pop     rsi
0x18000d607  pop     rbx
0x18000d608  retn
```
