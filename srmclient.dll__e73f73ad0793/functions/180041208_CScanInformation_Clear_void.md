# CScanInformation::Clear(void)

- ea: `0x180041208`
- end: `0x180041389`
- name: `?Clear@CScanInformation@@QEAAXXZ`
- size: `385`
- prototype: `void __fastcall(CScanInformation *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180040608`
- `0x180041df0`
- `0x18009ba9c`

## callees

- `0x180012210`
- `0x180016540`
- `0x180041208`
- `0x1800506cc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180041275`
- `ole32!CoTaskMemFree` at `0x1800412a5`
- `ole32!CoTaskMemFree` at `0x1800412ca`
- `ole32!CoTaskMemFree` at `0x1800412d5`
- `ole32!CoTaskMemFree` at `0x1800412e0`
- `ole32!CoTaskMemFree` at `0x1800412eb`
- `ole32!CoTaskMemFree` at `0x1800412f6`
- `ole32!CoTaskMemFree` at `0x180041301`
- `ole32!CoTaskMemFree` at `0x18004131f`
- `ole32!CoTaskMemFree` at `0x18004133d`
- `ole32!CoTaskMemFree` at `0x180041357`
- `ole32!CoTaskMemFree` at `0x180041275`
- `ole32!CoTaskMemFree` at `0x1800412a5`
- `ole32!CoTaskMemFree` at `0x1800412ca`
- `ole32!CoTaskMemFree` at `0x1800412d5`
- `ole32!CoTaskMemFree` at `0x1800412e0`
- `ole32!CoTaskMemFree` at `0x1800412eb`
- `ole32!CoTaskMemFree` at `0x1800412f6`
- `ole32!CoTaskMemFree` at `0x180041301`
- `ole32!CoTaskMemFree` at `0x18004131f`
- `ole32!CoTaskMemFree` at `0x18004133d`
- `ole32!CoTaskMemFree` at `0x180041357`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CScanInformation::Clear(CScanInformation *this)
{
  CScanInformation *v1; // rsi
  unsigned int i; // r15d
  __int64 v3; // rbp
  __int64 v4; // r14
  unsigned int v5; // r12d
  __int64 v6; // rsi
  unsigned int v7; // ebp
  __int64 v8; // rdi
  __int64 v9; // rbx
  CScanInformation *v10; // [rsp+20h] [rbp-48h] BYREF
  char v11; // [rsp+28h] [rbp-40h]

  v1 = this;
  CScanInformation::ClearScanInfoStructures(this);
  v10 = (CScanInformation *)((char *)v1 + 72);
  CSrmCriticalSection::Lock((LPCRITICAL_SECTION)((char *)v1 + 72));
  v11 = 1;
  if ( *((_QWORD *)v1 + 16) )
  {
    for ( i = 0; i < *((_DWORD *)v1 + 30); ++i )
    {
      v3 = 3LL * i;
      v4 = *((_QWORD *)v1 + 16);
      CoTaskMemFree(*(LPVOID *)(v4 + 24LL * i));
      if ( *(_QWORD *)(v4 + 24LL * i + 16) )
      {
        v5 = 0;
        if ( *(_DWORD *)(v4 + 24LL * i + 8) )
        {
          do
          {
            v6 = *(_QWORD *)(v4 + 8 * v3 + 16);
            CoTaskMemFree(*(LPVOID *)(v6 + 40LL * v5 + 8));
            if ( *(_QWORD *)(v6 + 40LL * v5 + 32) )
            {
              if ( *(_DWORD *)(v6 + 40LL * v5 + 24) )
              {
                v7 = 0;
                do
                {
                  v8 = 88LL * v7;
                  v9 = *(_QWORD *)(v6 + 40LL * v5 + 32);
                  CoTaskMemFree(*(LPVOID *)(v8 + v9));
                  CoTaskMemFree(*(LPVOID *)(v8 + v9 + 8));
                  CoTaskMemFree(*(LPVOID *)(v8 + v9 + 16));
                  CoTaskMemFree(*(LPVOID *)(v8 + v9 + 24));
                  CoTaskMemFree(*(LPVOID *)(v8 + v9 + 32));
                  CoTaskMemFree(*(LPVOID *)(v8 + v9 + 80));
                  ++v7;
                }
                while ( v7 < *(_DWORD *)(v6 + 40LL * v5 + 24) );
                v3 = 3LL * i;
              }
              CoTaskMemFree(*(LPVOID *)(v6 + 40LL * v5 + 32));
            }
            ++v5;
          }
          while ( v5 < *(_DWORD *)(v4 + 8 * v3 + 8) );
          v1 = this;
        }
        CoTaskMemFree(*(LPVOID *)(v4 + 8 * v3 + 16));
      }
    }
    CoTaskMemFree(*((LPVOID *)v1 + 16));
    *((_DWORD *)v1 + 30) = 0;
    *((_QWORD *)v1 + 16) = 0;
  }
  CSrmAutomaticLock::~CSrmAutomaticLock((LPCRITICAL_SECTION *)&v10);
}

```

## disassembly

```asm
0x180041208  mov     [rsp+arg_18], rbx
0x18004120d  mov     [rsp+arg_0], rcx
0x180041212  push    rbp
0x180041213  push    rsi
0x180041214  push    rdi
0x180041215  push    r12
0x180041217  push    r13
0x180041219  push    r14
0x18004121b  push    r15
0x18004121d  sub     rsp, 30h
0x180041221  mov     rsi, rcx
0x180041224  call    ?ClearScanInfoStructures@CScanInformation@@AEAAXXZ; CScanInformation::ClearScanInfoStructures(void)
0x180041229  lea     rcx, [rsi+48h]; lpCriticalSection
0x18004122d  mov     [rsp+68h+var_48], rcx
0x180041232  xor     ebx, ebx
0x180041234  mov     [rsp+68h+var_40], bl
0x180041238  call    ?Lock@CSrmCriticalSection@@QEAAXXZ; CSrmCriticalSection::Lock(void)
0x18004123d  mov     [rsp+68h+var_40], 1
0x180041242  cmp     [rsi+80h], rbx
0x180041249  jz      loc_180041367
0x18004124f  mov     r15d, ebx
0x180041252  cmp     [rsi+78h], ebx
0x180041255  jbe     loc_180041350
0x18004125b  mov     eax, r15d
0x18004125e  lea     rbp, [rax+rax*2]
0x180041262  mov     [rsp+68h+arg_10], rbp
0x18004126a  mov     r14, [rsi+80h]
0x180041271  mov     rcx, [r14+rbp*8]; pv
0x180041275  call    cs:__imp_CoTaskMemFree
0x18004127b  cmp     [r14+rbp*8+10h], rbx
0x180041280  jz      loc_180041343
0x180041286  mov     r12d, ebx
0x180041289  cmp     [r14+rbp*8+8], ebx
0x18004128e  jbe     loc_180041338
0x180041294  mov     eax, r12d
0x180041297  lea     r13, [rax+rax*4]
0x18004129b  mov     rsi, [r14+rbp*8+10h]
0x1800412a0  mov     rcx, [rsi+r13*8+8]; pv
0x1800412a5  call    cs:__imp_CoTaskMemFree
0x1800412ab  cmp     [rsi+r13*8+20h], rbx
0x1800412b0  jz      short loc_180041325
0x1800412b2  cmp     [rsi+r13*8+18h], ebx
0x1800412b7  jbe     short loc_18004131A
0x1800412b9  mov     ebp, ebx
0x1800412bb  mov     eax, ebp
0x1800412bd  imul    rdi, rax, 58h ; 'X'
0x1800412c1  mov     rbx, [rsi+r13*8+20h]
0x1800412c6  mov     rcx, [rdi+rbx]; pv
0x1800412ca  call    cs:__imp_CoTaskMemFree
0x1800412d0  mov     rcx, [rdi+rbx+8]; pv
0x1800412d5  call    cs:__imp_CoTaskMemFree
0x1800412db  mov     rcx, [rdi+rbx+10h]; pv
0x1800412e0  call    cs:__imp_CoTaskMemFree
0x1800412e6  mov     rcx, [rdi+rbx+18h]; pv
0x1800412eb  call    cs:__imp_CoTaskMemFree
0x1800412f1  mov     rcx, [rdi+rbx+20h]; pv
0x1800412f6  call    cs:__imp_CoTaskMemFree
0x1800412fc  mov     rcx, [rdi+rbx+50h]; pv
0x180041301  call    cs:__imp_CoTaskMemFree
0x180041307  inc     ebp
0x180041309  cmp     ebp, [rsi+r13*8+18h]
0x18004130e  jb      short loc_1800412BB
0x180041310  mov     rbp, [rsp+68h+arg_10]
0x180041318  xor     ebx, ebx
0x18004131a  mov     rcx, [rsi+r13*8+20h]; pv
0x18004131f  call    cs:__imp_CoTaskMemFree
0x180041325  inc     r12d
0x180041328  cmp     r12d, [r14+rbp*8+8]
0x18004132d  jb      loc_180041294
0x180041333  mov     rsi, [rsp+68h+arg_0]
0x180041338  mov     rcx, [r14+rbp*8+10h]; pv
0x18004133d  call    cs:__imp_CoTaskMemFree
0x180041343  inc     r15d
0x180041346  cmp     r15d, [rsi+78h]
0x18004134a  jb      loc_18004125B
0x180041350  mov     rcx, [rsi+80h]; pv
0x180041357  call    cs:__imp_CoTaskMemFree
0x18004135d  mov     [rsi+78h], ebx
0x180041360  mov     [rsi+80h], rbx
0x180041367  lea     rcx, [rsp+68h+var_48]; this
0x18004136c  call    ??1CSrmAutomaticLock@@QEAA@XZ; CSrmAutomaticLock::~CSrmAutomaticLock(void)
0x180041371  mov     rbx, [rsp+68h+arg_18]
0x180041379  add     rsp, 30h
0x18004137d  pop     r15
0x18004137f  pop     r14
0x180041381  pop     r13
0x180041383  pop     r12
0x180041385  pop     rdi
0x180041386  pop     rsi
0x180041387  pop     rbp
0x180041388  retn
```
