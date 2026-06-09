# CPropertyBagFieldsDeltaBatch::~CPropertyBagFieldsDeltaBatch(void)

- ea: `0x180040528`
- end: `0x180040602`
- name: `??1CPropertyBagFieldsDeltaBatch@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(CPropertyBagFieldsDeltaBatch *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180041f60`
- `0x1800a20ac`
- `0x1800ae4b0`
- `0x1800bdcb5`
- `0x1800d000a`
- `0x1800d30e3`

## callees

- `0x180040528`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18004056e`
- `ole32!CoTaskMemFree` at `0x180040581`
- `ole32!CoTaskMemFree` at `0x18004059e`
- `ole32!CoTaskMemFree` at `0x1800405a9`
- `ole32!CoTaskMemFree` at `0x1800405b4`
- `ole32!CoTaskMemFree` at `0x1800405c9`
- `ole32!CoTaskMemFree` at `0x1800405d4`
- `ole32!CoTaskMemFree` at `0x1800405ec`
- `ole32!CoTaskMemFree` at `0x18004056e`
- `ole32!CoTaskMemFree` at `0x180040581`
- `ole32!CoTaskMemFree` at `0x18004059e`
- `ole32!CoTaskMemFree` at `0x1800405a9`
- `ole32!CoTaskMemFree` at `0x1800405b4`
- `ole32!CoTaskMemFree` at `0x1800405c9`
- `ole32!CoTaskMemFree` at `0x1800405d4`
- `ole32!CoTaskMemFree` at `0x1800405ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CPropertyBagFieldsDeltaBatch::~CPropertyBagFieldsDeltaBatch(CPropertyBagFieldsDeltaBatch *this)
{
  unsigned __int64 i; // r15
  __int64 v3; // r14
  __int64 v4; // rdi
  __int64 v5; // rbx
  __int64 j; // r12
  __int64 v7; // rbx

  if ( *((_QWORD *)this + 1) )
  {
    for ( i = 0; i < *(unsigned int *)this; CoTaskMemFree(*(LPVOID *)(v3 + 40 * i++ + 32)) )
    {
      v3 = *((_QWORD *)this + 1);
      v4 = 0;
      v5 = v3 + 40 * i;
      if ( *(_DWORD *)(v5 + 4) )
      {
        do
        {
          CoTaskMemFree(*(LPVOID *)(*(_QWORD *)(v5 + 8) + 8 * v4));
          v4 = (unsigned int)(v4 + 1);
        }
        while ( (unsigned int)v4 < *(_DWORD *)(v3 + 40 * i + 4) );
      }
      CoTaskMemFree(*(LPVOID *)(v5 + 8));
      for ( j = 0; (unsigned int)j < *(_DWORD *)(v3 + 40 * i + 16); j = (unsigned int)(j + 1) )
      {
        v7 = *(_QWORD *)(v3 + 40 * i + 24);
        CoTaskMemFree(*(LPVOID *)(v7 + 40 * j));
        CoTaskMemFree(*(LPVOID *)(v7 + 40 * j + 8));
        CoTaskMemFree(*(LPVOID *)(v7 + 40 * j + 16));
      }
      CoTaskMemFree(*(LPVOID *)(v3 + 40 * i + 24));
    }
    CoTaskMemFree(*((LPVOID *)this + 1));
  }
}

```

## disassembly

```asm
0x180040528  push    rbx
0x18004052a  push    rbp
0x18004052b  push    rsi
0x18004052c  push    rdi
0x18004052d  push    r12
0x18004052f  push    r14
0x180040531  push    r15
0x180040533  sub     rsp, 20h
0x180040537  mov     rsi, rcx
0x18004053a  cmp     qword ptr [rcx+8], 0
0x18004053f  jz      loc_1800405F3
0x180040545  xor     r15d, r15d
0x180040548  cmp     [rcx], r15d
0x18004054b  jbe     loc_1800405E8
0x180040551  lea     rbp, [r15+r15*4]
0x180040555  mov     r14, [rsi+8]
0x180040559  xor     edi, edi
0x18004055b  lea     rbx, [r14+rbp*8]
0x18004055f  cmp     [r14+rbp*8+4], edi
0x180040564  jbe     short loc_18004057D
0x180040566  mov     rcx, [rbx+8]
0x18004056a  mov     rcx, [rcx+rdi*8]; pv
0x18004056e  call    cs:__imp_CoTaskMemFree
0x180040574  inc     edi
0x180040576  cmp     edi, [r14+rbp*8+4]
0x18004057b  jb      short loc_180040566
0x18004057d  mov     rcx, [rbx+8]; pv
0x180040581  call    cs:__imp_CoTaskMemFree
0x180040587  xor     r12d, r12d
0x18004058a  cmp     [r14+rbp*8+10h], r12d
0x18004058f  jbe     short loc_1800405C4
0x180040591  lea     rdi, [r12+r12*4]
0x180040595  mov     rbx, [r14+rbp*8+18h]
0x18004059a  mov     rcx, [rbx+rdi*8]; pv
0x18004059e  call    cs:__imp_CoTaskMemFree
0x1800405a4  mov     rcx, [rbx+rdi*8+8]; pv
0x1800405a9  call    cs:__imp_CoTaskMemFree
0x1800405af  mov     rcx, [rbx+rdi*8+10h]; pv
0x1800405b4  call    cs:__imp_CoTaskMemFree
0x1800405ba  inc     r12d
0x1800405bd  cmp     r12d, [r14+rbp*8+10h]
0x1800405c2  jb      short loc_180040591
0x1800405c4  mov     rcx, [r14+rbp*8+18h]; pv
0x1800405c9  call    cs:__imp_CoTaskMemFree
0x1800405cf  mov     rcx, [r14+rbp*8+20h]; pv
0x1800405d4  call    cs:__imp_CoTaskMemFree
0x1800405da  inc     r15
0x1800405dd  mov     eax, [rsi]
0x1800405df  cmp     r15, rax
0x1800405e2  jb      loc_180040551
0x1800405e8  mov     rcx, [rsi+8]; pv
0x1800405ec  call    cs:__imp_CoTaskMemFree
0x1800405f2  nop
0x1800405f3  add     rsp, 20h
0x1800405f7  pop     r15
0x1800405f9  pop     r14
0x1800405fb  pop     r12
0x1800405fd  pop     rdi
0x1800405fe  pop     rsi
0x1800405ff  pop     rbp
0x180040600  pop     rbx
0x180040601  retn
```
