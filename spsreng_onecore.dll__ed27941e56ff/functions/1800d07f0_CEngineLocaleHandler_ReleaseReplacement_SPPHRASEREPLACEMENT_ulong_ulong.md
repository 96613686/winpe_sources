# CEngineLocaleHandler::ReleaseReplacement(SPPHRASEREPLACEMENT * *,ulong,ulong)

- ea: `0x1800d07f0`
- end: `0x1800d08d5`
- name: `?ReleaseReplacement@CEngineLocaleHandler@@UEAAJPEAPEAUSPPHRASEREPLACEMENT@@KK@Z`
- size: `229`
- prototype: `int(CEngineLocaleHandler *__hidden this, struct SPPHRASEREPLACEMENT **, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e00`
- `0x1800d07f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800d0849`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1800d0849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d08a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d0879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d08a9`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandler::ReleaseReplacement(
        CEngineLocaleHandler *this,
        struct SPPHRASEREPLACEMENT **a2,
        unsigned int a3,
        unsigned int a4)
{
  void *v5; // rbx
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebp
  __int64 v8; // rdi
  unsigned int v9; // r15d
  __int64 v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rdx

  if ( a2 )
    v5 = *a2;
  else
    v5 = 0;
  v6 = a4 * (unsigned __int64)a3;
  if ( v6 > 0xFFFFFFFF )
    return (unsigned int)-2147024362;
  if ( (_DWORD)v6 )
  {
    v7 = 0;
    if ( !v5 )
    {
LABEL_19:
      operator delete(a2);
      return v7;
    }
    qsort(v5, (unsigned int)v6, 0x18u, CompReplacement);
    v8 = 0;
    v9 = v6 - 1;
    if ( (_DWORD)v6 == 1 )
      goto LABEL_16;
    do
    {
      v10 = 3 * v8;
      v11 = *((_QWORD *)v5 + 3 * v8 + 1);
      if ( v11 && v11 != *((_QWORD *)v5 + 3 * (unsigned int)(v8 + 1) + 1) )
        CoTaskMemFree(*((LPVOID *)v5 + 3 * v8 + 1));
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < v9 );
    if ( !(_DWORD)v8 )
    {
LABEL_16:
      v12 = 0;
    }
    else
    {
      v12 = (unsigned int)v8;
      if ( *((_QWORD *)v5 + v10 + 1) == *((_QWORD *)v5 + 3 * v8 + 1) )
      {
LABEL_18:
        operator delete(v5);
        goto LABEL_19;
      }
    }
    CoTaskMemFree(*((LPVOID *)v5 + 3 * v12 + 1));
    goto LABEL_18;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800d07f0  push    rbx
0x1800d07f2  push    rbp
0x1800d07f3  push    rsi
0x1800d07f4  push    rdi
0x1800d07f5  push    r14
0x1800d07f7  push    r15
0x1800d07f9  sub     rsp, 28h
0x1800d07fd  mov     r14, rdx
0x1800d0800  test    rdx, rdx
0x1800d0803  jz      short loc_1800D080A
0x1800d0805  mov     rbx, [rdx]
0x1800d0808  jmp     short loc_1800D080C
0x1800d080a  xor     ebx, ebx
0x1800d080c  mov     eax, r9d
0x1800d080f  mov     esi, r8d
0x1800d0812  imul    rsi, rax
0x1800d0816  mov     eax, 0FFFFFFFFh
0x1800d081b  cmp     rsi, rax
0x1800d081e  ja      loc_1800D08C1
0x1800d0824  test    esi, esi
0x1800d0826  jnz     short loc_1800D0832
0x1800d0828  mov     ebp, 80070057h
0x1800d082d  jmp     loc_1800D08C6
0x1800d0832  xor     ebp, ebp
0x1800d0834  test    rbx, rbx
0x1800d0837  jz      short loc_1800D08B7
0x1800d0839  mov     edx, esi; NumOfElements
0x1800d083b  lea     r9, CompReplacement; CompareFunction
0x1800d0842  lea     r8d, [rbp+18h]; SizeOfElements
0x1800d0846  mov     rcx, rbx; Base
0x1800d0849  call    cs:__imp_qsort
0x1800d084f  xor     edi, edi
0x1800d0851  lea     r15d, [rsi-1]
0x1800d0855  test    r15d, r15d
0x1800d0858  jz      short loc_1800D089E
0x1800d085a  lea     rsi, [rdi+rdi*2]
0x1800d085e  mov     rdx, [rbx+rsi*8+8]
0x1800d0863  test    rdx, rdx
0x1800d0866  jz      short loc_1800D087F
0x1800d0868  lea     eax, [rdi+1]
0x1800d086b  lea     rax, [rax+rax*2]
0x1800d086f  cmp     rdx, [rbx+rax*8+8]
0x1800d0874  jz      short loc_1800D087F
0x1800d0876  mov     rcx, rdx; pv
0x1800d0879  call    cs:__imp_CoTaskMemFree
0x1800d087f  inc     edi
0x1800d0881  cmp     edi, r15d
0x1800d0884  jb      short loc_1800D085A
0x1800d0886  test    edi, edi
0x1800d0888  jz      short loc_1800D089E
0x1800d088a  lea     rax, [rdi+rdi*2]
0x1800d088e  mov     edx, edi
0x1800d0890  mov     rcx, [rbx+rax*8+8]
0x1800d0895  cmp     [rbx+rsi*8+8], rcx
0x1800d089a  jz      short loc_1800D08AF
0x1800d089c  jmp     short loc_1800D08A0
0x1800d089e  xor     edx, edx
0x1800d08a0  lea     rcx, [rdx+rdx*2]
0x1800d08a4  mov     rcx, [rbx+rcx*8+8]; pv
0x1800d08a9  call    cs:__imp_CoTaskMemFree
0x1800d08af  mov     rcx, rbx; void *
0x1800d08b2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d08b7  mov     rcx, r14; void *
0x1800d08ba  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800d08bf  jmp     short loc_1800D08C6
0x1800d08c1  mov     ebp, 80070216h
0x1800d08c6  mov     eax, ebp
0x1800d08c8  add     rsp, 28h
0x1800d08cc  pop     r15
0x1800d08ce  pop     r14
0x1800d08d0  pop     rdi
0x1800d08d1  pop     rsi
0x1800d08d2  pop     rbp
0x1800d08d3  pop     rbx
0x1800d08d4  retn
```
