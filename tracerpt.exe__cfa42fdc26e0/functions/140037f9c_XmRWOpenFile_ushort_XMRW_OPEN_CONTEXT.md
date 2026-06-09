# XmRWOpenFile(ushort *,_XMRW_OPEN_CONTEXT *)

- ea: `0x140037f9c`
- end: `0x140038094`
- name: `?XmRWOpenFile@@YAKPEAGPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc, struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017398`
- `0x14002e418`
- `0x140035db4`

## callees

- `0x140037e2c`
- `0x140037f9c`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140038082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140038082`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140037fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038074`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140037fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038074`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140037fc0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140037fc0`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14003800f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14003800f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003806c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003806c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140037fe2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140037fe2`
- `XmlLite!CreateXmlReader` at `0x14003804b`
- `XmlLite!CreateXmlReader` at `0x14003804b`

## pseudocode

```c
__int64 __fastcall XmRWOpenFile(LPCWSTR lpSrc, struct _XMRW_OPEN_CONTEXT *a2)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rax
  unsigned __int16 *v6; // rsi
  unsigned int XmlReader; // ebx
  _QWORD *v8; // r14
  DWORD LastError; // eax
  HANDLE v10; // rax

  ProcessHeap = GetProcessHeap();
  v5 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x800u);
  v6 = v5;
  if ( v5 )
  {
    if ( ExpandEnvironmentStringsW(lpSrc, v5, 0x400u) - 1 > 0x3FE )
    {
      LastError = GetLastError();
    }
    else
    {
      XmlReader = XmRWGetViewOfFileEx(v6, a2);
      if ( XmlReader )
      {
LABEL_13:
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v6);
        return XmlReader;
      }
      v8 = (_QWORD *)((char *)a2 + 32);
      if ( CreateStreamOnHGlobal(*((HGLOBAL *)a2 + 2), 0, (LPSTREAM *)a2 + 4) )
      {
        XmlReader = 110;
        goto LABEL_13;
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v8 + 48LL))(*v8, *((unsigned int *)a2 + 2)) )
      {
        XmlReader = 25;
        goto LABEL_13;
      }
      XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, (void **)a2 + 3, 0);
      if ( XmlReader )
        goto LABEL_13;
      LastError = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)a2 + 3) + 24LL))(*((_QWORD *)a2 + 3), *v8);
    }
    XmlReader = LastError;
    goto LABEL_13;
  }
  return 14;
}

```

## disassembly

```asm
0x140037f9c  push    rbx
0x140037f9e  push    rsi
0x140037f9f  push    rdi
0x140037fa0  push    r14
0x140037fa2  sub     rsp, 28h
0x140037fa6  mov     rdi, rdx
0x140037fa9  mov     rbx, rcx
0x140037fac  call    cs:__imp_GetProcessHeap
0x140037fb2  mov     edx, 8; dwFlags
0x140037fb7  mov     r8d, 800h; dwBytes
0x140037fbd  mov     rcx, rax; hHeap
0x140037fc0  call    cs:__imp_HeapAlloc
0x140037fc6  mov     rsi, rax
0x140037fc9  test    rax, rax
0x140037fcc  jnz     short loc_140037FD6
0x140037fce  lea     ebx, [rax+0Eh]
0x140037fd1  jmp     loc_140038088
0x140037fd6  mov     r8d, 400h; nSize
0x140037fdc  mov     rdx, rsi; lpDst
0x140037fdf  mov     rcx, rbx; lpSrc
0x140037fe2  call    cs:__imp_ExpandEnvironmentStringsW
0x140037fe8  dec     eax
0x140037fea  cmp     eax, 3FEh
0x140037fef  ja      short loc_14003806C
0x140037ff1  mov     rdx, rdi; struct _XMRW_OPEN_CONTEXT *
0x140037ff4  mov     rcx, rsi; unsigned __int16 *
0x140037ff7  call    ?XmRWGetViewOfFileEx@@YAKPEAGPEAU_XMRW_OPEN_CONTEXT@@@Z; XmRWGetViewOfFileEx(ushort *,_XMRW_OPEN_CONTEXT *)
0x140037ffc  mov     ebx, eax
0x140037ffe  test    eax, eax
0x140038000  jnz     short loc_140038074
0x140038002  mov     rcx, [rdi+10h]; hGlobal
0x140038006  lea     r14, [rdi+20h]
0x14003800a  mov     r8, r14; ppstm
0x14003800d  xor     edx, edx; fDeleteOnRelease
0x14003800f  call    cs:__imp_CreateStreamOnHGlobal
0x140038015  test    eax, eax
0x140038017  jz      short loc_140038020
0x140038019  mov     ebx, 6Eh ; 'n'
0x14003801e  jmp     short loc_140038074
0x140038020  mov     rcx, [r14]
0x140038023  mov     edx, [rdi+8]
0x140038026  mov     rax, [rcx]
0x140038029  mov     rax, [rax+30h]
0x14003802d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038032  test    eax, eax
0x140038034  jz      short loc_14003803D
0x140038036  mov     ebx, 19h
0x14003803b  jmp     short loc_140038074
0x14003803d  xor     r8d, r8d; pMalloc
0x140038040  lea     rdx, [rdi+18h]; ppvObject
0x140038044  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x14003804b  call    cs:__imp_CreateXmlReader
0x140038051  mov     ebx, eax
0x140038053  test    eax, eax
0x140038055  jnz     short loc_140038074
0x140038057  mov     rcx, [rdi+18h]
0x14003805b  mov     rdx, [r14]
0x14003805e  mov     rax, [rcx]
0x140038061  mov     rax, [rax+18h]
0x140038065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003806a  jmp     short loc_140038072
0x14003806c  call    cs:__imp_GetLastError
0x140038072  mov     ebx, eax
0x140038074  call    cs:__imp_GetProcessHeap
0x14003807a  mov     r8, rsi; lpMem
0x14003807d  xor     edx, edx; dwFlags
0x14003807f  mov     rcx, rax; hHeap
0x140038082  call    cs:__imp_HeapFree
0x140038088  mov     eax, ebx
0x14003808a  add     rsp, 28h
0x14003808e  pop     r14
0x140038090  pop     rdi
0x140038091  pop     rsi
0x140038092  pop     rbx
0x140038093  retn
```
