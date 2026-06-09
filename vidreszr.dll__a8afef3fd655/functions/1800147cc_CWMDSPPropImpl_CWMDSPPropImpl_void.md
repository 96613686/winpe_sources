# CWMDSPPropImpl::~CWMDSPPropImpl(void)

- ea: `0x1800147cc`
- end: `0x18001486b`
- name: `??1CWMDSPPropImpl@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(CWMDSPPropImpl *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002c30`

## callees

- `0x1800019c0`
- `0x1800147cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001484e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001484e`
- `OLEAUT32!__imp_SysFreeString` at `0x180014834`
- `OLEAUT32!__imp_SysFreeString` at `0x180014834`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001481e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001481e`

## pseudocode

```c
void __fastcall CWMDSPPropImpl::~CWMDSPPropImpl(CWMDSPPropImpl *this)
{
  bool v1; // zf
  __int64 i; // rdi
  __int64 v4; // rax
  __int64 v5; // rbp
  void *v6; // rcx
  void *v7; // rcx

  v1 = *((_QWORD *)this + 3) == 0;
  *(_QWORD *)this = &CWMDSPPropImpl::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
    {
      v4 = *((_QWORD *)this + 2);
      v5 = *((_QWORD *)this + 3);
      if ( *(_WORD *)(96 * i + v4 + 20) == 8 )
      {
        SysFreeString(*(BSTR *)(v5 + 72 * i + 8));
        *(_QWORD *)(v5 + 72 * i + 8) = 0;
      }
      else if ( *(_WORD *)(96 * i + v4 + 20) == 65 )
      {
        v6 = *(void **)(v5 + 72 * i + 16);
        if ( v6 )
          CoTaskMemFree(v6);
        *(_QWORD *)(v5 + 72 * i + 16) = 0;
      }
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v7 = (void *)*((_QWORD *)this + 3);
  if ( v7 )
    operator delete(v7);
}

```

## disassembly

```asm
0x1800147cc  push    rbx
0x1800147ce  push    rbp
0x1800147cf  push    rsi
0x1800147d0  push    rdi
0x1800147d1  sub     rsp, 28h
0x1800147d5  cmp     qword ptr [rcx+18h], 0
0x1800147da  lea     rax, ??_7CWMDSPPropImpl@@6B@; const CWMDSPPropImpl::`vftable'
0x1800147e1  mov     [rcx], rax
0x1800147e4  mov     rbx, rcx
0x1800147e7  jz      short loc_18001484A
0x1800147e9  xor     edi, edi
0x1800147eb  cmp     [rcx+8], edi
0x1800147ee  jbe     short loc_18001484A
0x1800147f0  mov     rax, [rbx+10h]
0x1800147f4  lea     rcx, [rdi+rdi*2]
0x1800147f8  mov     rbp, [rbx+18h]
0x1800147fc  lea     rsi, [rdi+rdi*8]
0x180014800  shl     rcx, 5
0x180014804  cmp     word ptr [rcx+rax+14h], 8
0x18001480a  jz      short loc_18001482F
0x18001480c  cmp     word ptr [rcx+rax+14h], 41h ; 'A'
0x180014812  jnz     short loc_180014843
0x180014814  mov     rcx, [rbp+rsi*8+10h]; pv
0x180014819  test    rcx, rcx
0x18001481c  jz      short loc_180014824
0x18001481e  call    cs:__imp_CoTaskMemFree
0x180014824  mov     qword ptr [rbp+rsi*8+10h], 0
0x18001482d  jmp     short loc_180014843
0x18001482f  mov     rcx, [rbp+rsi*8+8]; bstrString
0x180014834  call    cs:__imp_SysFreeString
0x18001483a  mov     qword ptr [rbp+rsi*8+8], 0
0x180014843  inc     edi
0x180014845  cmp     edi, [rbx+8]
0x180014848  jb      short loc_1800147F0
0x18001484a  lea     rcx, [rbx+30h]; lpCriticalSection
0x18001484e  call    cs:__imp_DeleteCriticalSection
0x180014854  mov     rcx, [rbx+18h]; Block
0x180014858  test    rcx, rcx
0x18001485b  jz      short loc_180014862
0x18001485d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014862  add     rsp, 28h
0x180014866  pop     rdi
0x180014867  pop     rsi
0x180014868  pop     rbp
0x180014869  pop     rbx
0x18001486a  retn
```
