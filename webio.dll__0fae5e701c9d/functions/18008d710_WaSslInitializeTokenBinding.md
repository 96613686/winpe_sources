# WaSslInitializeTokenBinding

- ea: `0x18008d710`
- end: `0x18008d90d`
- name: `WaSslInitializeTokenBinding`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001db14`

## callees

- `0x180013820`
- `0x1800391c0`
- `0x1800722f0`
- `0x18008d710`
- `0x180092564`
- `0x1800971ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d76f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d76f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d881`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d8c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008d8c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d8ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d8ae`
- `TOKENBINDING!TokenBindingGetHighestSupportedVersion` at `0x18008d790`
- `TOKENBINDING!TokenBindingGetHighestSupportedVersion` at `0x18008d790`
- `TOKENBINDING!TokenBindingGetKeyTypesClient` at `0x18008d7cf`
- `TOKENBINDING!TokenBindingGetKeyTypesClient` at `0x18008d7cf`

## pseudocode

```c
__int64 WaSslInitializeTokenBinding()
{
  unsigned int v0; // ebx
  unsigned int HighestSupportedVersion; // edi
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  _BYTE *Heap; // rax
  unsigned int v6; // r8d
  _QWORD *i; // rax
  __int64 v8; // rdx
  HANDLE ProcessHeap; // rax
  _BYTE *v11; // [rsp+28h] [rbp-30h]
  LPVOID lpMem; // [rsp+30h] [rbp-28h] BYREF
  char v13; // [rsp+38h] [rbp-20h] BYREF
  _BYTE v14[7]; // [rsp+39h] [rbp-1Fh] BYREF

  v0 = 0;
  v11 = 0;
  lpMem = 0;
  v13 = 0;
  v14[0] = 0;
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_(1027, 32, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids);
  if ( !WaSslTokenBindingNegotiator )
  {
    AcquireSRWLockExclusive(&WaGlobalTokenBindingInitLock);
    if ( WaSslTokenBindingNegotiator )
    {
LABEL_20:
      ReleaseSRWLockExclusive(&WaGlobalTokenBindingInitLock);
      goto LABEL_21;
    }
    HighestSupportedVersion = TokenBindingGetHighestSupportedVersion(&v13, v14);
    if ( HighestSupportedVersion )
    {
      if ( (xmmword_1800AD710 & 8) == 0 )
      {
LABEL_9:
        v0 = HighestSupportedVersion;
        goto LABEL_20;
      }
      v2 = 33;
    }
    else
    {
      HighestSupportedVersion = TokenBindingGetKeyTypesClient(&lpMem);
      if ( !HighestSupportedVersion )
      {
        v4 = *(unsigned int *)lpMem + 4LL;
        if ( v4 <= 6 )
          LODWORD(v4) = 6;
        Heap = (_BYTE *)WxAllocateHeapEx(v3, (unsigned int)v4);
        v11 = Heap;
        if ( Heap )
        {
          v6 = 0;
          *Heap = v13;
          v11[1] = v14[0];
          *((_WORD *)v11 + 1) = *(_WORD *)lpMem;
          for ( i = lpMem; v6 < *(_DWORD *)lpMem; i = lpMem )
          {
            v8 = v6++;
            v11[v8 + 4] = *(_BYTE *)(i[1] + 4 * v8);
          }
          _InterlockedExchange(&WaSslTokenBindingNegotiatorSize, v4);
          _InterlockedExchange64(&WaSslTokenBindingNegotiator, (__int64)v11);
          v11 = 0;
        }
        else
        {
          v0 = 8;
        }
        goto LABEL_20;
      }
      if ( (xmmword_1800AD710 & 8) == 0 )
        goto LABEL_9;
      v2 = 34;
    }
    WPP_SF_d(515, v2, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, HighestSupportedVersion);
    goto LABEL_9;
  }
LABEL_21:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
    lpMem = 0;
  }
  if ( (xmmword_1800AD720 & 8) != 0 )
    WPP_SF_d(1027, 35, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x18008d710  push    rbp
0x18008d712  push    rbx
0x18008d713  push    rsi
0x18008d714  push    rdi
0x18008d715  mov     rbp, rsp
0x18008d718  sub     rsp, 58h
0x18008d71c  mov     rax, cs:__security_cookie
0x18008d723  xor     rax, rsp
0x18008d726  mov     [rbp+var_18], rax
0x18008d72a  xor     esi, esi
0x18008d72c  mov     ebx, esi
0x18008d72e  mov     [rbp+var_30], rsi
0x18008d732  mov     [rbp+lpMem], rsi
0x18008d736  mov     [rbp+var_20], sil
0x18008d73a  mov     [rbp+var_1F], sil
0x18008d73e  test    byte ptr cs:xmmword_1800AD720, 8
0x18008d745  jz      short loc_18008D75B
0x18008d747  lea     edx, [rsi+20h]
0x18008d74a  mov     ecx, 403h
0x18008d74f  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x18008d756  call    WPP_SF_
0x18008d75b  cmp     cs:WaSslTokenBindingNegotiator, rsi
0x18008d762  jnz     loc_18008D88D
0x18008d768  lea     rcx, WaGlobalTokenBindingInitLock; SRWLock
0x18008d76f  call    cs:__imp_AcquireSRWLockExclusive
0x18008d776  nop     dword ptr [rax+rax+00h]
0x18008d77b  cmp     cs:WaSslTokenBindingNegotiator, rsi
0x18008d782  jnz     loc_18008D87A
0x18008d788  lea     rdx, [rbp+var_1F]
0x18008d78c  lea     rcx, [rbp+var_20]
0x18008d790  call    cs:__imp_TokenBindingGetHighestSupportedVersion
0x18008d797  nop     dword ptr [rax+rax+00h]
0x18008d79c  mov     edi, eax
0x18008d79e  test    eax, eax
0x18008d7a0  jz      short loc_18008D7CB
0x18008d7a2  test    byte ptr cs:xmmword_1800AD710, 8
0x18008d7a9  jz      short loc_18008D7C4
0x18008d7ab  mov     edx, 21h ; '!'
0x18008d7b0  mov     ecx, 203h
0x18008d7b5  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x18008d7bc  mov     r9d, edi
0x18008d7bf  call    WPP_SF_d
0x18008d7c4  mov     ebx, edi
0x18008d7c6  jmp     loc_18008D87A
0x18008d7cb  lea     rcx, [rbp+lpMem]
0x18008d7cf  call    cs:__imp_TokenBindingGetKeyTypesClient
0x18008d7d6  nop     dword ptr [rax+rax+00h]
0x18008d7db  mov     edi, eax
0x18008d7dd  test    eax, eax
0x18008d7df  jz      short loc_18008D7F1
0x18008d7e1  test    byte ptr cs:xmmword_1800AD710, 8
0x18008d7e8  jz      short loc_18008D7C4
0x18008d7ea  mov     edx, 22h ; '"'
0x18008d7ef  jmp     short loc_18008D7B0
0x18008d7f1  mov     rax, [rbp+lpMem]
0x18008d7f5  mov     edi, [rax]
0x18008d7f7  add     rdi, 4
0x18008d7fb  cmp     rdi, 6
0x18008d7ff  ja      short loc_18008D806
0x18008d801  mov     edi, 6
0x18008d806  mov     edx, edi
0x18008d808  call    WxAllocateHeapEx
0x18008d80d  mov     [rbp+var_30], rax
0x18008d811  mov     rcx, rax
0x18008d814  test    rax, rax
0x18008d817  jnz     short loc_18008D81E
0x18008d819  lea     ebx, [rax+8]
0x18008d81c  jmp     short loc_18008D87A
0x18008d81e  mov     al, [rbp+var_20]
0x18008d821  mov     r8d, esi
0x18008d824  mov     [rcx], al
0x18008d826  mov     rcx, [rbp+var_30]
0x18008d82a  mov     al, [rbp+var_1F]
0x18008d82d  mov     [rcx+1], al
0x18008d830  mov     rax, [rbp+lpMem]
0x18008d834  movzx   ecx, word ptr [rax]
0x18008d837  mov     rax, [rbp+var_30]
0x18008d83b  mov     [rax+2], cx
0x18008d83f  mov     rax, [rbp+lpMem]
0x18008d843  cmp     [rax], esi
0x18008d845  jbe     short loc_18008D865
0x18008d847  mov     rax, [rax+8]
0x18008d84b  mov     edx, r8d
0x18008d84e  inc     r8d
0x18008d851  mov     cl, [rax+rdx*4]
0x18008d854  mov     rax, [rbp+var_30]
0x18008d858  mov     [rdx+rax+4], cl
0x18008d85c  mov     rax, [rbp+lpMem]
0x18008d860  cmp     r8d, [rax]
0x18008d863  jb      short loc_18008D847
0x18008d865  xchg    edi, cs:WaSslTokenBindingNegotiatorSize
0x18008d86b  mov     rax, [rbp+var_30]
0x18008d86f  xchg    rax, cs:WaSslTokenBindingNegotiator
0x18008d876  mov     [rbp+var_30], rsi
0x18008d87a  lea     rcx, WaGlobalTokenBindingInitLock; SRWLock
0x18008d881  call    cs:__imp_ReleaseSRWLockExclusive
0x18008d888  nop     dword ptr [rax+rax+00h]
0x18008d88d  cmp     [rbp+var_30], rsi
0x18008d891  jz      short loc_18008D8A8
0x18008d893  lea     rax, [rbp+var_30]
0x18008d897  lea     rcx, [rbp+var_38]
0x18008d89b  mov     [rbp+var_38], rax
0x18008d89f  call    WxFreeHeapEx
0x18008d8a4  mov     [rbp+var_30], rsi
0x18008d8a8  cmp     [rbp+lpMem], rsi
0x18008d8ac  jz      short loc_18008D8D3
0x18008d8ae  call    cs:__imp_GetProcessHeap
0x18008d8b5  nop     dword ptr [rax+rax+00h]
0x18008d8ba  mov     r8, [rbp+lpMem]; lpMem
0x18008d8be  xor     edx, edx; dwFlags
0x18008d8c0  mov     rcx, rax; hHeap
0x18008d8c3  call    cs:__imp_HeapFree
0x18008d8ca  nop     dword ptr [rax+rax+00h]
0x18008d8cf  mov     [rbp+lpMem], rsi
0x18008d8d3  test    byte ptr cs:xmmword_1800AD720, 8
0x18008d8da  jz      short loc_18008D8F5
0x18008d8dc  mov     edx, 23h ; '#'
0x18008d8e1  lea     r8, WPP_170392fd7cf134a4357a7b9a1157466f_Traceguids
0x18008d8e8  mov     ecx, 403h
0x18008d8ed  mov     r9d, ebx
0x18008d8f0  call    WPP_SF_d
0x18008d8f5  mov     eax, ebx
0x18008d8f7  mov     rcx, [rbp+var_18]
0x18008d8fb  xor     rcx, rsp; StackCookie
0x18008d8fe  call    __security_check_cookie
0x18008d903  add     rsp, 58h
0x18008d907  pop     rdi
0x18008d908  pop     rsi
0x18008d909  pop     rbx
0x18008d90a  pop     rbp
0x18008d90b  retn
```
