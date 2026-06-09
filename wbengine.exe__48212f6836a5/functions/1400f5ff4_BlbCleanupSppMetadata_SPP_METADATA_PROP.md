# BlbCleanupSppMetadata(_SPP_METADATA_PROP *)

- ea: `0x1400f5ff4`
- end: `0x1400f6135`
- name: `?BlbCleanupSppMetadata@@YAXPEAU_SPP_METADATA_PROP@@@Z`
- size: `321`
- prototype: `void __fastcall(struct _SPP_METADATA_PROP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140019fd0`
- `0x1400249b8`

## callees

- `0x140006ca8`
- `0x1400f5ff4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400f602b`
- `ole32!CoTaskMemFree` at `0x1400f604c`
- `ole32!CoTaskMemFree` at `0x1400f605d`
- `ole32!CoTaskMemFree` at `0x1400f6090`
- `ole32!CoTaskMemFree` at `0x1400f609b`
- `ole32!CoTaskMemFree` at `0x1400f60a6`
- `ole32!CoTaskMemFree` at `0x1400f60d0`
- `ole32!CoTaskMemFree` at `0x1400f60e0`
- `ole32!CoTaskMemFree` at `0x1400f60eb`
- `ole32!CoTaskMemFree` at `0x1400f60f6`
- `ole32!CoTaskMemFree` at `0x1400f610b`
- `ole32!CoTaskMemFree` at `0x1400f6120`
- `ole32!CoTaskMemFree` at `0x1400f602b`
- `ole32!CoTaskMemFree` at `0x1400f604c`
- `ole32!CoTaskMemFree` at `0x1400f605d`
- `ole32!CoTaskMemFree` at `0x1400f6090`
- `ole32!CoTaskMemFree` at `0x1400f609b`
- `ole32!CoTaskMemFree` at `0x1400f60a6`
- `ole32!CoTaskMemFree` at `0x1400f60d0`
- `ole32!CoTaskMemFree` at `0x1400f60e0`
- `ole32!CoTaskMemFree` at `0x1400f60eb`
- `ole32!CoTaskMemFree` at `0x1400f60f6`
- `ole32!CoTaskMemFree` at `0x1400f610b`
- `ole32!CoTaskMemFree` at `0x1400f6120`

## pseudocode

```c
void __fastcall BlbCleanupSppMetadata(LPVOID *a1)
{
  __int64 i; // rdi
  void *v3; // rcx
  __int64 j; // rbp
  LPVOID *v5; // rsi
  __int64 k; // r12
  _QWORD *v7; // r15
  void *v8; // rcx
  void *v9; // rcx

  if ( !a1 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbspputils.cpp", 0x262u, "pMetadata");
  if ( *a1 )
    CoTaskMemFree(*a1);
  if ( a1[2] )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a1 + 2); i = (unsigned int)(i + 1) )
    {
      v3 = (void *)*((_QWORD *)a1[2] + i);
      if ( v3 )
        CoTaskMemFree(v3);
    }
    CoTaskMemFree(a1[2]);
  }
  if ( a1[4] )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)a1 + 6); j = (unsigned int)(j + 1) )
    {
      v5 = (LPVOID *)a1[4];
      CoTaskMemFree(v5[10 * j + 5]);
      CoTaskMemFree(v5[10 * j + 6]);
      CoTaskMemFree(v5[10 * j + 7]);
      if ( v5[10 * j + 9] )
      {
        for ( k = 0; (unsigned int)k < HIDWORD(v5[10 * j + 8]); k = (unsigned int)(k + 1) )
        {
          v7 = v5[10 * j + 9];
          v8 = (void *)v7[5 * k];
          if ( v8 )
            CoTaskMemFree(v8);
          v9 = (void *)v7[5 * k + 1];
          if ( v9 )
            CoTaskMemFree(v9);
          CoTaskMemFree((LPVOID)v7[5 * k + 2]);
          CoTaskMemFree((LPVOID)v7[5 * k + 4]);
        }
        CoTaskMemFree(v5[10 * j + 9]);
      }
    }
    CoTaskMemFree(a1[4]);
  }
}

```

## disassembly

```asm
0x1400f5ff4  push    rbx
0x1400f5ff6  push    rbp
0x1400f5ff7  push    rsi
0x1400f5ff8  push    rdi
0x1400f5ff9  push    r12
0x1400f5ffb  push    r14
0x1400f5ffd  push    r15
0x1400f5fff  sub     rsp, 20h
0x1400f6003  mov     rbx, rcx
0x1400f6006  test    rcx, rcx
0x1400f6009  jnz     short loc_1400F6023
0x1400f600b  lea     r8, aPmetadata; "pMetadata"
0x1400f6012  mov     edx, 262h; unsigned int
0x1400f6017  lea     rcx, aBaseStorBlbEng_25; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1400f601e  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1400f6023  mov     rcx, [rbx]; pv
0x1400f6026  test    rcx, rcx
0x1400f6029  jz      short loc_1400F6031
0x1400f602b  call    cs:__imp_CoTaskMemFree
0x1400f6031  cmp     qword ptr [rbx+10h], 0
0x1400f6036  jz      short loc_1400F6063
0x1400f6038  xor     edi, edi
0x1400f603a  cmp     [rbx+8], edi
0x1400f603d  jbe     short loc_1400F6059
0x1400f603f  mov     rax, [rbx+10h]
0x1400f6043  mov     rcx, [rax+rdi*8]; pv
0x1400f6047  test    rcx, rcx
0x1400f604a  jz      short loc_1400F6052
0x1400f604c  call    cs:__imp_CoTaskMemFree
0x1400f6052  inc     edi
0x1400f6054  cmp     edi, [rbx+8]
0x1400f6057  jb      short loc_1400F603F
0x1400f6059  mov     rcx, [rbx+10h]; pv
0x1400f605d  call    cs:__imp_CoTaskMemFree
0x1400f6063  cmp     qword ptr [rbx+20h], 0
0x1400f6068  jz      loc_1400F6126
0x1400f606e  xor     ebp, ebp
0x1400f6070  cmp     [rbx+18h], ebp
0x1400f6073  jbe     loc_1400F611C
0x1400f6079  mov     rsi, [rbx+20h]
0x1400f607d  lea     rdi, ds:0[rbp*4]
0x1400f6085  add     rdi, rbp
0x1400f6088  add     rdi, rdi
0x1400f608b  mov     rcx, [rsi+rdi*8+28h]; pv
0x1400f6090  call    cs:__imp_CoTaskMemFree
0x1400f6096  mov     rcx, [rsi+rdi*8+30h]; pv
0x1400f609b  call    cs:__imp_CoTaskMemFree
0x1400f60a1  mov     rcx, [rsi+rdi*8+38h]; pv
0x1400f60a6  call    cs:__imp_CoTaskMemFree
0x1400f60ac  cmp     qword ptr [rsi+rdi*8+48h], 0
0x1400f60b2  jz      short loc_1400F6111
0x1400f60b4  xor     r12d, r12d
0x1400f60b7  cmp     [rsi+rdi*8+44h], r12d
0x1400f60bc  jbe     short loc_1400F6106
0x1400f60be  mov     r15, [rsi+rdi*8+48h]
0x1400f60c3  lea     r14, [r12+r12*4]
0x1400f60c7  mov     rcx, [r15+r14*8]; pv
0x1400f60cb  test    rcx, rcx
0x1400f60ce  jz      short loc_1400F60D6
0x1400f60d0  call    cs:__imp_CoTaskMemFree
0x1400f60d6  mov     rcx, [r15+r14*8+8]; pv
0x1400f60db  test    rcx, rcx
0x1400f60de  jz      short loc_1400F60E6
0x1400f60e0  call    cs:__imp_CoTaskMemFree
0x1400f60e6  mov     rcx, [r15+r14*8+10h]; pv
0x1400f60eb  call    cs:__imp_CoTaskMemFree
0x1400f60f1  mov     rcx, [r15+r14*8+20h]; pv
0x1400f60f6  call    cs:__imp_CoTaskMemFree
0x1400f60fc  inc     r12d
0x1400f60ff  cmp     r12d, [rsi+rdi*8+44h]
0x1400f6104  jb      short loc_1400F60BE
0x1400f6106  mov     rcx, [rsi+rdi*8+48h]; pv
0x1400f610b  call    cs:__imp_CoTaskMemFree
0x1400f6111  inc     ebp
0x1400f6113  cmp     ebp, [rbx+18h]
0x1400f6116  jb      loc_1400F6079
0x1400f611c  mov     rcx, [rbx+20h]; pv
0x1400f6120  call    cs:__imp_CoTaskMemFree
0x1400f6126  add     rsp, 20h
0x1400f612a  pop     r15
0x1400f612c  pop     r14
0x1400f612e  pop     r12
0x1400f6130  pop     rdi
0x1400f6131  pop     rsi
0x1400f6132  pop     rbp
0x1400f6133  pop     rbx
0x1400f6134  retn
```
