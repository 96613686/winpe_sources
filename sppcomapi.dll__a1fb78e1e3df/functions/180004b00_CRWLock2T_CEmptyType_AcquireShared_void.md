# CRWLock2T<CEmptyType>::AcquireShared(void)

- ea: `0x180004b00`
- end: `0x180004c86`
- name: `?AcquireShared@?$CRWLock2T@VCEmptyType@@@@QEAAXXZ`
- size: `390`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050f0`
- `0x18001c300`
- `0x18001c470`
- `0x18001c5e0`
- `0x18001c750`
- `0x18001c8c0`
- `0x18001f5f0`
- `0x18001f760`

## callees

- `0x180004b00`
- `0x180004eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004b22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004c36`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004c4f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004c4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004c6c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004c6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b10`

## pseudocode

```c
void __fastcall CRWLock2T<CEmptyType>::AcquireShared(__int64 a1)
{
  DWORD CurrentThreadId; // ebp
  DWORD *v3; // rax
  DWORD v4; // ecx
  __int64 v5; // r8
  DWORD *v6; // rdi
  __int64 v7; // rcx
  int v8; // esi
  int v9; // r10d
  DWORD *v10; // rdx
  __int64 v11; // r9
  bool v12; // zf
  __int64 v13; // rcx
  _DWORD *v14; // r8

  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  while ( 1 )
  {
    while ( 1 )
    {
      v3 = (DWORD *)(a1 + 80);
      if ( !*(_DWORD *)(a1 + 64) )
      {
        *v3 = CurrentThreadId;
        *(_DWORD *)(a1 + 84) = 1;
        *(_DWORD *)(a1 + 64) = 1;
        goto LABEL_39;
      }
      v4 = *v3;
      if ( !*(_DWORD *)(a1 + 76) )
        break;
      if ( v4 == CurrentThreadId )
      {
        ++*(_DWORD *)(a1 + 84);
        goto LABEL_39;
      }
      v5 = *(_QWORD *)(a1 + 88);
      v6 = 0;
      if ( v5 && (v7 = 0, *(_DWORD *)(a1 + 96)) )
      {
        while ( *(_DWORD *)(v5 + 8 * v7) )
        {
          v7 = (unsigned int)(v7 + 1);
          if ( (unsigned int)v7 >= *(_DWORD *)(a1 + 96) )
            goto LABEL_9;
        }
        v6 = (DWORD *)(v5 + 8 * v7);
      }
      else
      {
LABEL_9:
        CRWLock2T<CEmptyType>::ExpandOwnerTable(a1);
      }
      if ( v6 )
        goto LABEL_11;
    }
    v9 = *(_DWORD *)(a1 + 72);
    v10 = 0;
    v6 = 0;
    if ( v4 == CurrentThreadId )
      v10 = (DWORD *)(a1 + 80);
    if ( !v9 && !v4 )
      v6 = (DWORD *)(a1 + 80);
    v11 = *(_QWORD *)(a1 + 88);
    if ( v11 )
    {
      v12 = v10 == 0;
      if ( v10 )
        goto LABEL_29;
      v13 = 0;
      if ( *(_DWORD *)(a1 + 96) )
      {
        while ( 1 )
        {
          v14 = (_DWORD *)(v11 + 8 * v13);
          if ( *v14 == CurrentThreadId )
            break;
          if ( !v6 && !*v14 )
            v6 = (DWORD *)(v11 + 8 * v13);
          v13 = (unsigned int)(v13 + 1);
          if ( (unsigned int)v13 >= *(_DWORD *)(a1 + 96) )
            goto LABEL_28;
        }
        v10 = (DWORD *)(v11 + 8 * v13);
      }
    }
LABEL_28:
    v12 = v10 == 0;
LABEL_29:
    if ( !v12 )
      v6 = v10;
    if ( v6 )
      break;
    CRWLock2T<CEmptyType>::ExpandOwnerTable(a1);
  }
  if ( *v6 == CurrentThreadId )
  {
    ++v6[1];
  }
  else
  {
    if ( v9 )
    {
LABEL_11:
      v8 = 0;
      *v6 = CurrentThreadId;
      v6[1] = 1;
      ++*(_DWORD *)(a1 + 68);
      goto LABEL_40;
    }
    *v6 = CurrentThreadId;
    v6[1] = 1;
    ++*(_DWORD *)(a1 + 64);
  }
LABEL_39:
  v8 = 1;
LABEL_40:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( !v8 )
  {
    if ( WaitForSingleObject(*(HANDLE *)(a1 + 56), 0x337F9800u) )
      RaiseException(0xC0000194, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x180004b00  push    rbx
0x180004b02  push    rbp
0x180004b03  push    rsi
0x180004b04  push    rdi
0x180004b05  push    r12
0x180004b07  push    r14
0x180004b09  sub     rsp, 28h
0x180004b0d  mov     rbx, rcx
0x180004b10  call    cs:__imp_GetCurrentThreadId
0x180004b17  nop     dword ptr [rax+rax+00h]
0x180004b1c  lea     rcx, [rbx+8]; lpCriticalSection
0x180004b20  mov     ebp, eax
0x180004b22  call    cs:__imp_EnterCriticalSection
0x180004b29  nop     dword ptr [rax+rax+00h]
0x180004b2e  mov     r12d, 1
0x180004b34  cmp     dword ptr [rbx+40h], 0
0x180004b38  lea     rax, [rbx+50h]
0x180004b3c  jbe     loc_180004C25
0x180004b42  cmp     dword ptr [rbx+4Ch], 0
0x180004b46  mov     ecx, [rax]
0x180004b48  jz      short loc_180004B97
0x180004b4a  cmp     ecx, ebp
0x180004b4c  jz      loc_180004C00
0x180004b52  mov     r8, [rbx+58h]
0x180004b56  xor     edi, edi
0x180004b58  test    r8, r8
0x180004b5b  jz      short loc_180004B74
0x180004b5d  xor     ecx, ecx
0x180004b5f  cmp     [rbx+60h], ecx
0x180004b62  jbe     short loc_180004B74
0x180004b64  lea     rdx, [r8+rcx*8]
0x180004b68  cmp     [rdx], edi
0x180004b6a  jz      short loc_180004B92
0x180004b6c  add     ecx, r12d
0x180004b6f  cmp     ecx, [rbx+60h]
0x180004b72  jb      short loc_180004B64
0x180004b74  mov     rcx, rbx
0x180004b77  call    ?ExpandOwnerTable@?$CRWLock2T@VCEmptyType@@@@AEAAXXZ; CRWLock2T<CEmptyType>::ExpandOwnerTable(void)
0x180004b7c  test    rdi, rdi
0x180004b7f  jz      short loc_180004B34
0x180004b81  xor     esi, esi
0x180004b83  mov     [rdi], ebp
0x180004b85  mov     [rdi+4], r12d
0x180004b89  add     [rbx+44h], r12d
0x180004b8d  jmp     loc_180004C32
0x180004b92  mov     rdi, rdx
0x180004b95  jmp     short loc_180004B7C
0x180004b97  mov     r10d, [rbx+48h]
0x180004b9b  xor     edx, edx
0x180004b9d  xor     edi, edi
0x180004b9f  cmp     ecx, ebp
0x180004ba1  cmovz   rdx, rax
0x180004ba5  test    r10d, r10d
0x180004ba8  jnz     short loc_180004BB0
0x180004baa  test    ecx, ecx
0x180004bac  cmovz   rdi, rax
0x180004bb0  mov     r9, [rbx+58h]
0x180004bb4  test    r9, r9
0x180004bb7  jz      short loc_180004BE7
0x180004bb9  test    rdx, rdx
0x180004bbc  jnz     short loc_180004BEA
0x180004bbe  xor     ecx, ecx
0x180004bc0  cmp     [rbx+60h], ecx
0x180004bc3  jbe     short loc_180004BE7
0x180004bc5  lea     r8, [r9+rcx*8]
0x180004bc9  cmp     [r8], ebp
0x180004bcc  jz      short loc_180004BE4
0x180004bce  test    rdi, rdi
0x180004bd1  jnz     short loc_180004BDA
0x180004bd3  cmp     [r8], edi
0x180004bd6  cmovz   rdi, r8
0x180004bda  add     ecx, r12d
0x180004bdd  cmp     ecx, [rbx+60h]
0x180004be0  jb      short loc_180004BC5
0x180004be2  jmp     short loc_180004BE7
0x180004be4  mov     rdx, r8
0x180004be7  test    rdx, rdx
0x180004bea  cmovnz  rdi, rdx
0x180004bee  test    rdi, rdi
0x180004bf1  jnz     short loc_180004C06
0x180004bf3  mov     rcx, rbx
0x180004bf6  call    ?ExpandOwnerTable@?$CRWLock2T@VCEmptyType@@@@AEAAXXZ; CRWLock2T<CEmptyType>::ExpandOwnerTable(void)
0x180004bfb  jmp     loc_180004B34
0x180004c00  add     [rbx+54h], r12d
0x180004c04  jmp     short loc_180004C2F
0x180004c06  cmp     [rdi], ebp
0x180004c08  jnz     short loc_180004C10
0x180004c0a  add     [rdi+4], r12d
0x180004c0e  jmp     short loc_180004C2F
0x180004c10  test    r10d, r10d
0x180004c13  jnz     loc_180004B81
0x180004c19  mov     [rdi], ebp
0x180004c1b  mov     [rdi+4], r12d
0x180004c1f  add     [rbx+40h], r12d
0x180004c23  jmp     short loc_180004C2F
0x180004c25  mov     [rax], ebp
0x180004c27  mov     [rbx+54h], r12d
0x180004c2b  mov     [rbx+40h], r12d
0x180004c2f  mov     esi, r12d
0x180004c32  lea     rcx, [rbx+8]; lpCriticalSection
0x180004c36  call    cs:__imp_LeaveCriticalSection
0x180004c3d  nop     dword ptr [rax+rax+00h]
0x180004c42  test    esi, esi
0x180004c44  jnz     short loc_180004C78
0x180004c46  mov     rcx, [rbx+38h]; hHandle
0x180004c4a  mov     edx, 337F9800h; dwMilliseconds
0x180004c4f  call    cs:__imp_WaitForSingleObject
0x180004c56  nop     dword ptr [rax+rax+00h]
0x180004c5b  test    eax, eax
0x180004c5d  jz      short loc_180004C78
0x180004c5f  xor     r9d, r9d; lpArguments
0x180004c62  xor     r8d, r8d; nNumberOfArguments
0x180004c65  xor     edx, edx; dwExceptionFlags
0x180004c67  mov     ecx, 0C0000194h; dwExceptionCode
0x180004c6c  call    cs:__imp_RaiseException
0x180004c73  nop     dword ptr [rax+rax+00h]
0x180004c78  add     rsp, 28h
0x180004c7c  pop     r14
0x180004c7e  pop     r12
0x180004c80  pop     rdi
0x180004c81  pop     rsi
0x180004c82  pop     rbp
0x180004c83  pop     rbx
0x180004c84  retn
```
