# SystemParametersInfoAsync(uint,uint,void *,ulong,uint,CDimmedWindow *,void * *)

- ea: `0x18003188c`
- end: `0x180031998`
- name: `?SystemParametersInfoAsync@@YAXIIPEAXKIPEAVCDimmedWindow@@PEAPEAX@Z`
- size: `268`
- prototype: `void(unsigned int, unsigned int, void *, unsigned int, unsigned int, struct CDimmedWindow *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180019b78`
- `0x18001acc4`

## callees

- `0x1800035f4`
- `0x1800036c0`
- `0x18003188c`
- `0x180036324`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031985`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031985`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800318c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031921`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800318c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031921`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800318fe`
- `USER32!GetThreadDpiAwarenessContext` at `0x1800318fe`

## pseudocode

```c
void __fastcall SystemParametersInfoAsync(
        int a1,
        int a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        struct CDimmedWindow *a6,
        void **hObject)
{
  void **v7; // rdi
  SIZE_T v9; // rbp
  struct SPIS_INFO *v12; // rax
  struct SPIS_INFO *v13; // rbx
  unsigned int (*v14)(void *); // rcx
  volatile signed __int32 *v15; // rax
  HLOCAL v16; // rax

  v7 = hObject;
  v9 = a4;
  if ( hObject )
    *hObject = 0;
  v12 = (struct SPIS_INFO *)LocalAlloc(0x40u, 0x28u);
  v13 = v12;
  if ( v12 )
  {
    *((_QWORD *)v12 + 2) = a3;
    *((_DWORD *)v12 + 1) = a1;
    *((_DWORD *)v12 + 2) = a2;
    *(_DWORD *)v12 = v9 != 0;
    *((_DWORD *)v12 + 3) = a5;
    *((_QWORD *)v12 + 3) = a6;
    *((_QWORD *)v12 + 4) = GetThreadDpiAwarenessContext();
    v15 = (volatile signed __int32 *)*((_QWORD *)v13 + 3);
    if ( v15 )
      _InterlockedIncrement(v15);
    if ( *(_DWORD *)v13 )
    {
      v16 = LocalAlloc(0x40u, v9);
      *((_QWORD *)v13 + 2) = v16;
      if ( !v16 )
      {
        *((_QWORD *)v13 + 2) = a3;
        *(_DWORD *)v13 = 0;
        SystemParametersInfoAsync_WorkerThread(v13);
        return;
      }
      memcpy_0(v16, a3, v9);
    }
    hObject = 0;
    if ( SPICreateThread(v14, v13, (void **)&hObject) && hObject )
    {
      if ( v7 )
        *v7 = hObject;
      else
        CloseHandle(hObject);
    }
  }
}

```

## disassembly

```asm
0x18003188c  push    rbx
0x18003188e  push    rbp
0x18003188f  push    rsi
0x180031890  push    rdi
0x180031891  push    r14
0x180031893  push    r15
0x180031895  sub     rsp, 28h
0x180031899  mov     rdi, [rsp+58h+hObject]
0x1800318a1  mov     rsi, r8
0x1800318a4  mov     ebp, r9d
0x1800318a7  mov     r14d, edx
0x1800318aa  mov     r15d, ecx
0x1800318ad  test    rdi, rdi
0x1800318b0  jz      short loc_1800318B9
0x1800318b2  mov     qword ptr [rdi], 0
0x1800318b9  mov     edx, 28h ; '('; uBytes
0x1800318be  lea     ecx, [rdx+18h]; uFlags
0x1800318c1  call    cs:__imp_LocalAlloc
0x1800318c7  mov     rbx, rax
0x1800318ca  test    rax, rax
0x1800318cd  jz      loc_18003198B
0x1800318d3  xor     ecx, ecx
0x1800318d5  mov     [rax+10h], rsi
0x1800318d9  mov     [rax+4], r15d
0x1800318dd  test    ebp, ebp
0x1800318df  mov     [rax+8], r14d
0x1800318e3  setnz   cl
0x1800318e6  mov     [rax], ecx
0x1800318e8  mov     ecx, [rsp+58h+arg_20]
0x1800318ef  mov     [rax+0Ch], ecx
0x1800318f2  mov     rax, [rsp+58h+arg_28]
0x1800318fa  mov     [rbx+18h], rax
0x1800318fe  call    cs:__imp_GetThreadDpiAwarenessContext
0x180031904  mov     [rbx+20h], rax
0x180031908  mov     rax, [rbx+18h]
0x18003190c  test    rax, rax
0x18003190f  jz      short loc_180031914
0x180031911  lock inc dword ptr [rax]
0x180031914  cmp     dword ptr [rbx], 0
0x180031917  jz      short loc_18003194E
0x180031919  mov     rdx, rbp; uBytes
0x18003191c  mov     ecx, 40h ; '@'; uFlags
0x180031921  call    cs:__imp_LocalAlloc
0x180031927  mov     [rbx+10h], rax
0x18003192b  test    rax, rax
0x18003192e  jnz     short loc_180031940
0x180031930  mov     rcx, rbx; struct SPIS_INFO *
0x180031933  mov     [rbx+10h], rsi
0x180031937  mov     [rbx], eax
0x180031939  call    ?SystemParametersInfoAsync_WorkerThread@@YAKPEAX@Z; SystemParametersInfoAsync_WorkerThread(void *)
0x18003193e  jmp     short loc_18003198B
0x180031940  mov     r8, rbp; Size
0x180031943  mov     rdx, rsi; Src
0x180031946  mov     rcx, rax; void *
0x180031949  call    memcpy_0
0x18003194e  lea     r8, [rsp+58h+hObject]; void **
0x180031956  mov     [rsp+58h+hObject], 0
0x180031962  mov     rdx, rbx; void *
0x180031965  call    ?SPICreateThread@@YA_NP6AKPEAX@Z0PEAPEAX@Z; SPICreateThread(ulong (*)(void *),void *,void * *)
0x18003196a  test    al, al
0x18003196c  jz      short loc_18003198B
0x18003196e  mov     rcx, [rsp+58h+hObject]; hObject
0x180031976  test    rcx, rcx
0x180031979  jz      short loc_18003198B
0x18003197b  test    rdi, rdi
0x18003197e  jz      short loc_180031985
0x180031980  mov     [rdi], rcx
0x180031983  jmp     short loc_18003198B
0x180031985  call    cs:__imp_CloseHandle
0x18003198b  add     rsp, 28h
0x18003198f  pop     r15
0x180031991  pop     r14
0x180031993  pop     rdi
0x180031994  pop     rsi
0x180031995  pop     rbp
0x180031996  pop     rbx
0x180031997  retn
```
