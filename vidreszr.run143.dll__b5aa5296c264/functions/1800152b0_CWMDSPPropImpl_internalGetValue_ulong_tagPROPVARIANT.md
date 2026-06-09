# CWMDSPPropImpl::internalGetValue(ulong,tagPROPVARIANT *)

- ea: `0x1800152b0`
- end: `0x1800153a7`
- name: `?internalGetValue@CWMDSPPropImpl@@MEAAJKPEAUtagPROPVARIANT@@@Z`
- size: `247`
- prototype: `__int64 __fastcall(CWMDSPPropImpl *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009300`

## callees

- `0x1800152b0`
- `0x180015905`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001537d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001537d`
- `OLEAUT32!__imp_SysFreeString` at `0x180015372`
- `OLEAUT32!__imp_SysFreeString` at `0x180015388`
- `OLEAUT32!__imp_SysFreeString` at `0x180015372`
- `OLEAUT32!__imp_SysFreeString` at `0x180015388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015320`

## pseudocode

```c
__int64 __fastcall CWMDSPPropImpl::internalGetValue(CWMDSPPropImpl *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int64 v3; // rsi
  __int64 v5; // rdi
  BYTE *pData; // rcx
  unsigned int v7; // eax
  BYTE *v8; // rax
  OLECHAR *bstrVal; // rcx
  BSTR v10; // rbp

  v3 = *((_QWORD *)this + 3);
  v5 = 9LL * a2;
  switch ( a3->vt )
  {
    case 3u:
    case 4u:
      goto LABEL_21;
    case 5u:
LABEL_10:
      a3->hVal.QuadPart = *(_QWORD *)(v3 + 72LL * a2 + 8);
      return 0;
    case 8u:
      bstrVal = a3->bstrVal;
      v10 = 0;
      if ( *(_QWORD *)(v3 + 72LL * a2 + 8) )
      {
        SysFreeString(bstrVal);
        v10 = SysAllocString(*(const OLECHAR **)(v3 + 8 * v5 + 8));
      }
      else
      {
        SysFreeString(bstrVal);
      }
      a3->hVal.QuadPart = (LONGLONG)v10;
      return 0;
    case 0xBu:
      a3->iVal = *(_WORD *)(v3 + 72LL * a2 + 8);
      return 0;
    case 0x13u:
LABEL_21:
      a3->lVal = *(_DWORD *)(v3 + 72LL * a2 + 8);
      return 0;
    case 0x14u:
      goto LABEL_10;
    case 0x41u:
      pData = a3->bstrblobVal.pData;
      if ( pData )
        CoTaskMemFree(pData);
      v7 = *(_DWORD *)(v3 + 8 * v5 + 8);
      a3->lVal = v7;
      a3->bstrblobVal.pData = 0;
      if ( v7 )
      {
        v8 = (BYTE *)CoTaskMemAlloc(v7);
        a3->bstrblobVal.pData = v8;
        if ( v8 )
          memcpy_0(v8, *(const void **)(v3 + 8 * v5 + 16), a3->ulVal);
      }
      break;
    case 0x48u:
      goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1800152b0  push    rbx
0x1800152b2  push    rbp
0x1800152b3  push    rsi
0x1800152b4  push    rdi
0x1800152b5  sub     rsp, 28h
0x1800152b9  mov     rsi, [rcx+18h]
0x1800152bd  mov     rbx, r8
0x1800152c0  movzx   ecx, word ptr [r8]
0x1800152c4  mov     eax, edx
0x1800152c6  lea     rdi, [rax+rax*8]
0x1800152ca  sub     ecx, 3
0x1800152cd  jz      loc_180015394
0x1800152d3  sub     ecx, 1
0x1800152d6  jz      loc_180015394
0x1800152dc  sub     ecx, 1
0x1800152df  jz      short loc_180015307
0x1800152e1  sub     ecx, 3
0x1800152e4  jz      short loc_180015365
0x1800152e6  sub     ecx, 3
0x1800152e9  jz      short loc_180015359
0x1800152eb  sub     ecx, 8
0x1800152ee  jz      loc_180015394
0x1800152f4  sub     ecx, 1
0x1800152f7  jz      short loc_180015307
0x1800152f9  sub     ecx, 2Dh ; '-'
0x1800152fc  jz      short loc_180015315
0x1800152fe  cmp     ecx, 7
0x180015301  jnz     loc_18001539C
0x180015307  mov     rax, [rsi+rdi*8+8]
0x18001530c  mov     [r8+8], rax
0x180015310  jmp     loc_18001539C
0x180015315  mov     rcx, [r8+10h]; pv
0x180015319  xor     ebp, ebp
0x18001531b  test    rcx, rcx
0x18001531e  jz      short loc_180015326
0x180015320  call    cs:__imp_CoTaskMemFree
0x180015326  mov     eax, [rsi+rdi*8+8]
0x18001532a  mov     [rbx+8], eax
0x18001532d  mov     [rbx+10h], rbp
0x180015331  test    eax, eax
0x180015333  jz      short loc_18001539C
0x180015335  mov     ecx, eax; cb
0x180015337  call    cs:__imp_CoTaskMemAlloc
0x18001533d  mov     [rbx+10h], rax
0x180015341  test    rax, rax
0x180015344  jz      short loc_18001539C
0x180015346  mov     r8d, [rbx+8]; Size
0x18001534a  mov     rcx, rax; void *
0x18001534d  mov     rdx, [rsi+rdi*8+10h]; Src
0x180015352  call    memcpy_0
0x180015357  jmp     short loc_18001539C
0x180015359  movzx   eax, word ptr [rsi+rdi*8+8]
0x18001535e  mov     [r8+8], ax
0x180015363  jmp     short loc_18001539C
0x180015365  mov     rcx, [r8+8]; bstrString
0x180015369  xor     ebp, ebp
0x18001536b  cmp     [rsi+rdi*8+8], rbp
0x180015370  jz      short loc_180015388
0x180015372  call    cs:__imp_SysFreeString
0x180015378  mov     rcx, [rsi+rdi*8+8]; psz
0x18001537d  call    cs:__imp_SysAllocString
0x180015383  mov     rbp, rax
0x180015386  jmp     short loc_18001538E
0x180015388  call    cs:__imp_SysFreeString
0x18001538e  mov     [rbx+8], rbp
0x180015392  jmp     short loc_18001539C
0x180015394  mov     eax, [rsi+rdi*8+8]
0x180015398  mov     [r8+8], eax
0x18001539c  xor     eax, eax
0x18001539e  add     rsp, 28h
0x1800153a2  pop     rdi
0x1800153a3  pop     rsi
0x1800153a4  pop     rbp
0x1800153a5  pop     rbx
0x1800153a6  retn
```
