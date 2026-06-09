# WimRemoveOverlay

- ea: `0x14002b77c`
- end: `0x14002b9b8`
- name: `WimRemoveOverlay`
- size: `572`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400263f0`
- `0x1400273c0`

## callees

- `0x14000fce4`
- `0x1400116c0`
- `0x1400119c0`
- `0x14002b404`
- `0x14002b77c`
- `0x14002bdec`
- `0x14003c578`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002b95a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b970`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b95a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b970`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b821`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002b821`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b984`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b984`
- `FLTMGR!FltClose` at `0x14002b998`
- `FLTMGR!FltClose` at `0x14002b998`

## pseudocode

```c
__int64 __fastcall WimRemoveOverlay(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  __int64 result; // rax
  _DWORD *v5; // r15
  char *v6; // r14
  unsigned int v7; // ebx
  HANDLE v8; // rdi
  PVOID v9; // rsi
  size_t v10; // rdi
  char *PoolWithTag; // rax
  unsigned int v12; // esi
  ULONG v13; // r13d
  char *v15; // r9
  unsigned int v16; // eax
  size_t v17; // rcx
  unsigned int *v18; // r12
  _DWORD *v19; // rdi
  unsigned int v20; // esi
  _DWORD *v21; // rax
  int v22; // eax
  HANDLE FileHandle; // [rsp+30h] [rbp-28h] BYREF
  PVOID P; // [rsp+38h] [rbp-20h] BYREF
  size_t v25; // [rsp+40h] [rbp-18h]
  __int64 v27; // [rsp+A8h] [rbp+50h] BYREF
  SIZE_T NumberOfBytes; // [rsp+B0h] [rbp+58h] BYREF
  PVOID Object; // [rsp+B8h] [rbp+60h] BYREF

  v27 = a2;
  LODWORD(NumberOfBytes) = 0;
  P = 0;
  FileHandle = 0;
  Object = 0;
  v3 = a1;
  result = WimReadOverlayConfig(a1, 0, &FileHandle, (PFILE_OBJECT *)&Object, &P, (__int64)&NumberOfBytes);
  if ( (int)result < 0 )
    return result;
  v5 = P;
  if ( WimFindOverlayInfo(P, &v27) )
  {
    v10 = (unsigned int)NumberOfBytes;
    PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x66637077u);
    v6 = PoolWithTag;
    if ( PoolWithTag )
    {
      v12 = v5[2];
      memset(PoolWithTag, 0, v10);
      v13 = 24;
      *(_OWORD *)v6 = *(_OWORD *)v5;
      *((_QWORD *)v6 + 2) = *((_QWORD *)v5 + 2);
      if ( (*((_DWORD *)v6 + 3))-- != 1 )
      {
        v13 = v12 * *((_DWORD *)v6 + 3) + 24;
        if ( v5[3] )
        {
          v15 = v6 + 24;
          v16 = 0;
          v17 = v12;
          P = v6 + 24;
          LODWORD(NumberOfBytes) = 0;
          v18 = v5 + 6;
          v25 = v12;
          do
          {
            if ( *(_QWORD *)v18 != a2 )
            {
              v19 = (_DWORD *)((char *)v5 + v18[2]);
              v20 = v19[2];
              memmove(v15, v18, v17);
              v21 = P;
              *((_DWORD *)P + 2) = v13;
              v21[3] = v20;
              memmove(&v6[v13], v19, v20);
              v13 += v20;
              v17 = v25;
              v16 = NumberOfBytes;
              v15 = (char *)P + v25;
              P = (char *)P + v25;
            }
            ++v16;
            v18 = (unsigned int *)((char *)v18 + v17);
            LODWORD(NumberOfBytes) = v16;
          }
          while ( v16 < v5[3] );
          v3 = a1;
        }
      }
      v22 = WimWriteOverlayConfig(v3, FileHandle, (struct _FILE_OBJECT *)Object, v6, v13);
      v9 = 0;
      v8 = 0;
      v7 = v22;
      if ( v22 < 0 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Zd(
          WPP_GLOBAL_Control->AttachedDevice,
          49,
          (unsigned int)WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids,
          v3 + 64,
          v22);
      goto LABEL_18;
    }
    v7 = -1073741670;
  }
  else
  {
    v6 = 0;
    v7 = -1073741275;
  }
  v8 = FileHandle;
  v9 = Object;
LABEL_18:
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( v9 )
    ObfDereferenceObject(v9);
  if ( v8 )
    FltClose(v8);
  return v7;
}

```

## disassembly

```asm
0x14002b77c  mov     [rsp-40h+arg_8], rdx
0x14002b781  mov     [rsp-40h+arg_0], rcx
0x14002b786  push    rbp
0x14002b787  push    rbx
0x14002b788  push    rsi
0x14002b789  push    rdi
0x14002b78a  push    r12
0x14002b78c  push    r13
0x14002b78e  push    r14
0x14002b790  push    r15
0x14002b792  mov     rbp, rsp
0x14002b795  sub     rsp, 58h
0x14002b799  lea     rax, [rbp+NumberOfBytes]
0x14002b79d  mov     dword ptr [rbp+NumberOfBytes], 0
0x14002b7a4  mov     [rsp+58h+var_30], rax
0x14002b7a9  lea     r9, [rbp+Object]
0x14002b7ad  lea     rax, [rbp+P]
0x14002b7b1  mov     [rbp+P], 0
0x14002b7b9  mov     rbx, rdx
0x14002b7bc  mov     [rsp+58h+var_38], rax
0x14002b7c1  lea     r8, [rbp+FileHandle]
0x14002b7c5  mov     [rbp+FileHandle], 0
0x14002b7cd  xor     edx, edx
0x14002b7cf  mov     [rbp+Object], 0
0x14002b7d7  mov     r12, rcx
0x14002b7da  call    WimReadOverlayConfig
0x14002b7df  test    eax, eax
0x14002b7e1  js      loc_14002B9A6
0x14002b7e7  mov     r15, [rbp+P]
0x14002b7eb  lea     rdx, [rbp+arg_8]
0x14002b7ef  mov     rcx, r15
0x14002b7f2  call    WimFindOverlayInfo
0x14002b7f7  test    rax, rax
0x14002b7fa  jnz     short loc_14002B811
0x14002b7fc  xor     r14d, r14d
0x14002b7ff  mov     ebx, 0C0000225h
0x14002b804  mov     rdi, [rbp+FileHandle]
0x14002b808  mov     rsi, [rbp+Object]
0x14002b80c  jmp     loc_14002B950
0x14002b811  mov     edi, dword ptr [rbp+NumberOfBytes]
0x14002b814  mov     r8d, 66637077h; Tag
0x14002b81a  mov     edx, edi; NumberOfBytes
0x14002b81c  mov     ecx, 1; PoolType
0x14002b821  call    cs:__imp_ExAllocatePoolWithTag
0x14002b828  nop     dword ptr [rax+rax+00h]
0x14002b82d  mov     r14, rax
0x14002b830  test    rax, rax
0x14002b833  jnz     short loc_14002B83C
0x14002b835  mov     ebx, 0C000009Ah
0x14002b83a  jmp     short loc_14002B804
0x14002b83c  mov     esi, [r15+8]
0x14002b840  mov     r8, rdi; Size
0x14002b843  xor     edx, edx; Val
0x14002b845  mov     rcx, r14; void *
0x14002b848  call    memset
0x14002b84d  movups  xmm0, xmmword ptr [r15]
0x14002b851  mov     r13d, 18h
0x14002b857  movups  xmmword ptr [r14], xmm0
0x14002b85b  movsd   xmm1, qword ptr [r15+10h]
0x14002b861  movsd   qword ptr [r14+10h], xmm1
0x14002b867  add     dword ptr [r14+0Ch], 0FFFFFFFFh
0x14002b86c  mov     eax, [r14+0Ch]
0x14002b870  jz      loc_14002B8FC
0x14002b876  imul    eax, esi
0x14002b879  add     r13d, eax
0x14002b87c  cmp     dword ptr [r15+0Ch], 0
0x14002b881  jbe     short loc_14002B8FC
0x14002b883  lea     r9, [r14+18h]
0x14002b887  xor     eax, eax
0x14002b889  mov     ecx, esi
0x14002b88b  mov     [rbp+P], r9
0x14002b88f  mov     dword ptr [rbp+NumberOfBytes], eax
0x14002b892  lea     r12, [r15+18h]
0x14002b896  mov     [rbp+var_18], rcx
0x14002b89a  cmp     [r12], rbx
0x14002b89e  jz      short loc_14002B8EA
0x14002b8a0  mov     edi, [r12+8]
0x14002b8a5  mov     r8, rcx; Size
0x14002b8a8  add     rdi, r15
0x14002b8ab  mov     rdx, r12; Src
0x14002b8ae  mov     rcx, r9; void *
0x14002b8b1  mov     esi, [rdi+8]
0x14002b8b4  call    memmove
0x14002b8b9  mov     rax, [rbp+P]
0x14002b8bd  mov     r8d, esi; Size
0x14002b8c0  mov     ecx, r13d
0x14002b8c3  mov     rdx, rdi; Src
0x14002b8c6  add     rcx, r14; void *
0x14002b8c9  mov     [rax+8], r13d
0x14002b8cd  mov     [rax+0Ch], esi
0x14002b8d0  call    memmove
0x14002b8d5  mov     r9, [rbp+P]
0x14002b8d9  add     r13d, esi
0x14002b8dc  mov     rcx, [rbp+var_18]
0x14002b8e0  mov     eax, dword ptr [rbp+NumberOfBytes]
0x14002b8e3  add     r9, rcx
0x14002b8e6  mov     [rbp+P], r9
0x14002b8ea  inc     eax
0x14002b8ec  add     r12, rcx
0x14002b8ef  mov     dword ptr [rbp+NumberOfBytes], eax
0x14002b8f2  cmp     eax, [r15+0Ch]
0x14002b8f6  jb      short loc_14002B89A
0x14002b8f8  mov     r12, [rbp+arg_0]
0x14002b8fc  mov     r8, [rbp+Object]
0x14002b900  mov     r9, r14
0x14002b903  mov     rdx, [rbp+FileHandle]
0x14002b907  mov     rcx, r12
0x14002b90a  mov     dword ptr [rsp+58h+var_38], r13d
0x14002b90f  call    WimWriteOverlayConfig
0x14002b914  xor     esi, esi
0x14002b916  xor     edi, edi
0x14002b918  mov     ebx, eax
0x14002b91a  test    eax, eax
0x14002b91c  jns     short loc_14002B950
0x14002b91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b925  test    dword ptr [rcx+2Ch], 400h
0x14002b92c  jz      short loc_14002B950
0x14002b92e  cmp     byte ptr [rcx+29h], 2
0x14002b932  jb      short loc_14002B950
0x14002b934  mov     rcx, [rcx+18h]
0x14002b938  lea     r9, [r12+40h]
0x14002b93d  lea     edx, [rsi+31h]
0x14002b940  mov     dword ptr [rsp+58h+var_38], eax
0x14002b944  lea     r8, WPP_8be5f4e5626c39736f1e2e11a2a58b62_Traceguids
0x14002b94b  call    WPP_SF_Zd
0x14002b950  test    r15, r15
0x14002b953  jz      short loc_14002B966
0x14002b955  xor     edx, edx; Tag
0x14002b957  mov     rcx, r15; P
0x14002b95a  call    cs:__imp_ExFreePoolWithTag
0x14002b961  nop     dword ptr [rax+rax+00h]
0x14002b966  test    r14, r14
0x14002b969  jz      short loc_14002B97C
0x14002b96b  xor     edx, edx; Tag
0x14002b96d  mov     rcx, r14; P
0x14002b970  call    cs:__imp_ExFreePoolWithTag
0x14002b977  nop     dword ptr [rax+rax+00h]
0x14002b97c  test    rsi, rsi
0x14002b97f  jz      short loc_14002B990
0x14002b981  mov     rcx, rsi; Object
0x14002b984  call    cs:__imp_ObfDereferenceObject
0x14002b98b  nop     dword ptr [rax+rax+00h]
0x14002b990  test    rdi, rdi
0x14002b993  jz      short loc_14002B9A4
0x14002b995  mov     rcx, rdi; FileHandle
0x14002b998  call    cs:__imp_FltClose
0x14002b99f  nop     dword ptr [rax+rax+00h]
0x14002b9a4  mov     eax, ebx
0x14002b9a6  add     rsp, 58h
0x14002b9aa  pop     r15
0x14002b9ac  pop     r14
0x14002b9ae  pop     r13
0x14002b9b0  pop     r12
0x14002b9b2  pop     rdi
0x14002b9b3  pop     rsi
0x14002b9b4  pop     rbx
0x14002b9b5  pop     rbp
0x14002b9b6  retn
```
