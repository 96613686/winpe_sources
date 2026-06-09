# GetClientList

- ea: `0x1800068ac`
- end: `0x180006a05`
- name: `GetClientList`
- size: `345`
- prototype: `__int64 __fastcall(int, _DWORD **)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180017be0`
- `0x18001b1dc`
- `0x18001b4c4`
- `0x180024fc8`
- `0x1800330a8`

## callees

- `0x1800068ac`
- `0x18001c7c0`
- `0x18002c8d4`
- `0x18003fb7c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000693a`
- `KERNEL32!HeapAlloc` at `0x18000693a`
- `KERNEL32!GetCurrentThreadId` at `0x1800068e1`
- `KERNEL32!GetCurrentThreadId` at `0x180006986`
- `KERNEL32!GetCurrentThreadId` at `0x1800069c3`
- `KERNEL32!GetCurrentThreadId` at `0x1800068e1`
- `KERNEL32!GetCurrentThreadId` at `0x180006986`
- `KERNEL32!GetCurrentThreadId` at `0x1800069c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800069ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800069e9`
- `KERNEL32!LeaveCriticalSection` at `0x1800069ac`
- `KERNEL32!LeaveCriticalSection` at `0x1800069e9`
- `KERNEL32!EnterCriticalSection` at `0x1800068d1`
- `KERNEL32!EnterCriticalSection` at `0x1800068d1`

## pseudocode

```c
__int64 __fastcall GetClientList(int a1, _DWORD **a2)
{
  _DWORD *v2; // rbx
  __int64 v4; // rdi
  int v6; // r14d
  size_t v7; // rdx
  __int64 i; // rsi
  char *v9; // rax
  _DWORD *v10; // rbp
  size_t v11; // rdx
  __int64 result; // rax
  size_t v13; // rdx

  v2 = *a2;
  v4 = 0;
  v6 = 8;
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 2953;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v7, "i\\server\\line.c");
  for ( i = qword_180051908; i; i = *(_QWORD *)(i + 208) )
  {
    if ( !a1 || (*(_BYTE *)(i + 216) & 1) != 0 )
    {
      if ( (_DWORD)v4 == v6 )
      {
        v6 *= 2;
        v9 = (char *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)(8 * v6 + 8));
        v10 = v9;
        if ( !v9 )
        {
          dword_1800519F8 = 2976;
          dword_1800519FC = GetCurrentThreadId();
          StringCbCopyA(byte_1800519E8, v11, "i\\server\\line.c");
          LeaveCriticalSection(&CriticalSection);
          return 2147483716LL;
        }
        memcpy_0(v9 + 8, v2 + 2, 8LL * (unsigned int)v4);
        if ( v2 != *a2 )
          ServerFree(v2);
        v2 = v10;
      }
      *(_QWORD *)&v2[2 * v4 + 2] = i;
      v4 = (unsigned int)(v4 + 1);
    }
  }
  dword_1800519F8 = 2999;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v13, "i\\server\\line.c");
  LeaveCriticalSection(&CriticalSection);
  *v2 = v4;
  result = 0;
  *a2 = v2;
  return result;
}

```

## disassembly

```asm
0x1800068ac  push    rbx
0x1800068ae  push    rbp
0x1800068af  push    rsi
0x1800068b0  push    rdi
0x1800068b1  push    r12
0x1800068b3  push    r14
0x1800068b5  push    r15
0x1800068b7  sub     rsp, 20h
0x1800068bb  mov     rbx, [rdx]
0x1800068be  mov     r12d, ecx
0x1800068c1  xor     edi, edi
0x1800068c3  lea     rcx, CriticalSection; lpCriticalSection
0x1800068ca  mov     r15, rdx
0x1800068cd  lea     r14d, [rdi+8]
0x1800068d1  call    cs:__imp_EnterCriticalSection
0x1800068d7  mov     cs:dword_1800519E0, 0B89h
0x1800068e1  call    cs:__imp_GetCurrentThreadId
0x1800068e7  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x1800068ee  mov     cs:dword_1800519E4, eax
0x1800068f4  lea     rcx, pszDest; pszDest
0x1800068fb  call    StringCbCopyA
0x180006900  mov     rsi, cs:qword_180051908
0x180006907  test    rsi, rsi
0x18000690a  jz      loc_1800069B9
0x180006910  test    r12d, r12d
0x180006913  jz      short loc_18000691E
0x180006915  test    byte ptr [rsi+0D8h], 1
0x18000691c  jz      short loc_180006973
0x18000691e  cmp     edi, r14d
0x180006921  jnz     short loc_18000696C
0x180006923  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18000692a  add     r14d, r14d
0x18000692d  mov     edx, 8; dwFlags
0x180006932  lea     r8d, ds:8[r14*8]; dwBytes
0x18000693a  call    cs:__imp_HeapAlloc
0x180006940  mov     rbp, rax
0x180006943  test    rax, rax
0x180006946  jz      short loc_18000697C
0x180006948  mov     r8d, edi
0x18000694b  lea     rdx, [rbx+8]; Src
0x18000694f  shl     r8, 3; Size
0x180006953  lea     rcx, [rax+8]; void *
0x180006957  call    memcpy_0
0x18000695c  cmp     rbx, [r15]
0x18000695f  jz      short loc_180006969
0x180006961  mov     rcx, rbx; lpMem
0x180006964  call    ServerFree
0x180006969  mov     rbx, rbp
0x18000696c  mov     [rbx+rdi*8+8], rsi
0x180006971  inc     edi
0x180006973  mov     rsi, [rsi+0D0h]
0x18000697a  jmp     short loc_180006907
0x18000697c  mov     cs:dword_1800519F8, 0BA0h
0x180006986  call    cs:__imp_GetCurrentThreadId
0x18000698c  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x180006993  mov     cs:dword_1800519FC, eax
0x180006999  lea     rcx, byte_1800519E8; pszDest
0x1800069a0  call    StringCbCopyA
0x1800069a5  lea     rcx, CriticalSection; lpCriticalSection
0x1800069ac  call    cs:__imp_LeaveCriticalSection
0x1800069b2  mov     eax, 80000044h
0x1800069b7  jmp     short loc_1800069F6
0x1800069b9  mov     cs:dword_1800519F8, 0BB7h
0x1800069c3  call    cs:__imp_GetCurrentThreadId
0x1800069c9  lea     r8, aPrintscanTapiS_4+0Dh; pszSrc
0x1800069d0  mov     cs:dword_1800519FC, eax
0x1800069d6  lea     rcx, byte_1800519E8; pszDest
0x1800069dd  call    StringCbCopyA
0x1800069e2  lea     rcx, CriticalSection; lpCriticalSection
0x1800069e9  call    cs:__imp_LeaveCriticalSection
0x1800069ef  mov     [rbx], edi
0x1800069f1  xor     eax, eax
0x1800069f3  mov     [r15], rbx
0x1800069f6  add     rsp, 20h
0x1800069fa  pop     r15
0x1800069fc  pop     r14
0x1800069fe  pop     r12
0x180006a00  pop     rdi
0x180006a01  pop     rsi
0x180006a02  pop     rbp
0x180006a03  pop     rbx
0x180006a04  retn
```
