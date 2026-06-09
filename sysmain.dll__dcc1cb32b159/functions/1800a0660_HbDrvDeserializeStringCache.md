# HbDrvDeserializeStringCache

- ea: `0x1800a0660`
- end: `0x1800a0816`
- name: `HbDrvDeserializeStringCache`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800a2dc8`

## callees

- `0x18001bfcc`
- `0x18001c020`
- `0x18001eeb0`
- `0x180021e0c`
- `0x18003a2ac`
- `0x1800a0660`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a07e7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a07e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a0742`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a07d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a0742`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a07d3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0758`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a0758`

## pseudocode

```c
__int64 __fastcall HbDrvDeserializeStringCache(__int64 a1)
{
  unsigned int v2; // esi
  void *v3; // rdi
  __int64 v4; // r9
  unsigned int File; // ebx
  unsigned int v6; // ebx
  _WORD v8[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v9[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h]
  int v11; // [rsp+60h] [rbp-A0h]
  int v12; // [rsp+78h] [rbp-88h]
  wchar_t pszDest[264]; // [rsp+90h] [rbp-70h] BYREF

  v8[0] = 0;
  v2 = 0;
  v3 = 0;
  memset_0(v9, 0, 0x48u);
  v10 = -1;
  StringCchPrintfW(pszDest, 0x104u, L"%s\\%s", *(_QWORD *)&PfSvcGlobals + 888LL, L"HybridDrivePopulate.lstx");
  File = PfsBcCreateFile((__int64)v9, pszDest, 0, v4, 0);
  if ( !File )
  {
    do
    {
      File = PfsBcReadFile(v9, v8, 2);
      if ( File )
        break;
      v6 = 2 * v8[0];
      if ( v2 < v6 )
      {
        if ( v3 )
          HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v3);
        v3 = HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v6);
        if ( !v3 )
        {
          File = 8;
          goto LABEL_17;
        }
        v2 = v6;
      }
      File = PfsBcReadFile(v9, v3, v6);
      if ( File )
        break;
      if ( !PfScStringInsertEx(a1 + 96, v3, v8[0]) )
      {
        File = 8;
        break;
      }
    }
    while ( v12 || v11 != 0x10000 );
    if ( v3 )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v3);
  }
LABEL_17:
  PfsBcClose(v9);
  DeleteFileW(pszDest);
  return File;
}

```

## disassembly

```asm
0x1800a0660  mov     [rsp-8+arg_8], rbx
0x1800a0665  mov     [rsp-8+arg_10], rsi
0x1800a066a  push    rbp
0x1800a066b  push    rdi
0x1800a066c  push    r14
0x1800a066e  lea     rbp, [rsp-1B0h]
0x1800a0676  sub     rsp, 2B0h
0x1800a067d  mov     rax, cs:__security_cookie
0x1800a0684  xor     rax, rsp
0x1800a0687  mov     [rbp+1C0h+var_20], rax
0x1800a068e  xor     eax, eax
0x1800a0690  mov     r14, rcx
0x1800a0693  xor     edx, edx; Val
0x1800a0695  mov     [rsp+2C0h+var_290], ax
0x1800a069a  lea     rcx, [rsp+2C0h+var_280]; void *
0x1800a069f  xor     esi, esi
0x1800a06a1  xor     edi, edi
0x1800a06a3  lea     r8d, [rax+48h]; Size
0x1800a06a7  call    memset_0
0x1800a06ac  mov     r9, cs:PfSvcGlobals
0x1800a06b3  lea     rax, aHybriddrivepop; "HybridDrivePopulate.lstx"
0x1800a06ba  add     r9, 378h
0x1800a06c1  mov     [rsp+2C0h+var_278], 0FFFFFFFFFFFFFFFFh
0x1800a06ca  lea     r8, aSS; "%s\\%s"
0x1800a06d1  mov     [rsp+2C0h+var_2A0], rax
0x1800a06d6  mov     edx, 104h; cchDest
0x1800a06db  lea     rcx, [rbp+1C0h+pszDest]; pszDest
0x1800a06df  call    StringCchPrintfW
0x1800a06e4  xor     r8d, r8d
0x1800a06e7  mov     dword ptr [rsp+2C0h+var_2A0], esi
0x1800a06eb  lea     rdx, [rbp+1C0h+pszDest]
0x1800a06ef  lea     rcx, [rsp+2C0h+var_280]
0x1800a06f4  call    PfsBcCreateFile
0x1800a06f9  mov     ebx, eax
0x1800a06fb  test    eax, eax
0x1800a06fd  jnz     loc_1800A07D9
0x1800a0703  mov     r8d, 2
0x1800a0709  lea     rdx, [rsp+2C0h+var_290]
0x1800a070e  lea     rcx, [rsp+2C0h+var_280]
0x1800a0713  call    PfsBcReadFile
0x1800a0718  mov     ebx, eax
0x1800a071a  test    eax, eax
0x1800a071c  jnz     loc_1800A07BE
0x1800a0722  movzx   ebx, [rsp+2C0h+var_290]
0x1800a0727  add     ebx, ebx
0x1800a0729  cmp     esi, ebx
0x1800a072b  jnb     short loc_1800A0768
0x1800a072d  test    rdi, rdi
0x1800a0730  jz      short loc_1800A0748
0x1800a0732  mov     rcx, cs:PfSvcGlobals
0x1800a0739  mov     r8, rdi; lpMem
0x1800a073c  xor     edx, edx; dwFlags
0x1800a073e  mov     rcx, [rcx+58h]; hHeap
0x1800a0742  call    cs:__imp_HeapFree
0x1800a0748  mov     rcx, cs:PfSvcGlobals
0x1800a074f  xor     edx, edx; dwFlags
0x1800a0751  mov     r8d, ebx; dwBytes
0x1800a0754  mov     rcx, [rcx+58h]; hHeap
0x1800a0758  call    cs:__imp_HeapAlloc
0x1800a075e  mov     rdi, rax
0x1800a0761  test    rax, rax
0x1800a0764  jz      short loc_1800A07B2
0x1800a0766  mov     esi, ebx
0x1800a0768  mov     r8d, ebx
0x1800a076b  lea     rcx, [rsp+2C0h+var_280]
0x1800a0770  mov     rdx, rdi
0x1800a0773  call    PfsBcReadFile
0x1800a0778  mov     ebx, eax
0x1800a077a  test    eax, eax
0x1800a077c  jnz     short loc_1800A07BE
0x1800a077e  movzx   r8d, [rsp+2C0h+var_290]
0x1800a0784  lea     rcx, [r14+60h]
0x1800a0788  xor     r9d, r9d
0x1800a078b  mov     rdx, rdi
0x1800a078e  call    PfScStringInsertEx
0x1800a0793  test    rax, rax
0x1800a0796  jz      short loc_1800A07B9
0x1800a0798  cmp     [rsp+2C0h+var_248], ebx
0x1800a079c  jnz     loc_1800A0703
0x1800a07a2  cmp     [rsp+2C0h+var_260], 10000h
0x1800a07aa  jnz     loc_1800A0703
0x1800a07b0  jmp     short loc_1800A07BE
0x1800a07b2  mov     ebx, 8
0x1800a07b7  jmp     short loc_1800A07D9
0x1800a07b9  mov     ebx, 8
0x1800a07be  test    rdi, rdi
0x1800a07c1  jz      short loc_1800A07D9
0x1800a07c3  mov     rcx, cs:PfSvcGlobals
0x1800a07ca  mov     r8, rdi; lpMem
0x1800a07cd  xor     edx, edx; dwFlags
0x1800a07cf  mov     rcx, [rcx+58h]; hHeap
0x1800a07d3  call    cs:__imp_HeapFree
0x1800a07d9  lea     rcx, [rsp+2C0h+var_280]
0x1800a07de  call    PfsBcClose
0x1800a07e3  lea     rcx, [rbp+1C0h+pszDest]; lpFileName
0x1800a07e7  call    cs:__imp_DeleteFileW
0x1800a07ed  mov     eax, ebx
0x1800a07ef  mov     rcx, [rbp+1C0h+var_20]
0x1800a07f6  xor     rcx, rsp; StackCookie
0x1800a07f9  call    __security_check_cookie
0x1800a07fe  lea     r11, [rsp+2C0h+var_10]
0x1800a0806  mov     rbx, [r11+28h]
0x1800a080a  mov     rsi, [r11+30h]
0x1800a080e  mov     rsp, r11
0x1800a0811  pop     r14
0x1800a0813  pop     rdi
0x1800a0814  pop     rbp
0x1800a0815  retn
```
