# CSpObjectToken::~CSpObjectToken(void)

- ea: `0x18001bb88`
- end: `0x18001bd08`
- name: `??1CSpObjectToken@@QEAA@XZ`
- size: `384`
- prototype: `void __fastcall(CSpObjectToken *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180083250`

## callees

- `0x18001bb88`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bcf5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bcf5`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001bbff`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001bc80`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001bbff`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18001bc80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bbf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bbf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bc59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bcda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bc59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001bcda`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSpObjectToken::~CSpObjectToken(CSpObjectToken *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  LPVOID *v5; // rbx
  const void *v6; // rdi
  HANDLE ProcessHeap; // rax
  SIZE_T v8; // rax
  SIZE_T v9; // rax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rdi
  __int64 i; // rcx
  LPVOID *v14; // rbx
  const void *v15; // rdi
  HANDLE v16; // rax
  SIZE_T v17; // rax
  SIZE_T v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  _WORD *v21; // rdi
  __int64 j; // rcx

  v2 = *((_QWORD *)this + 15);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 13);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (LPVOID *)((char *)this + 96);
  v6 = (const void *)*((_QWORD *)this + 12);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapSize(ProcessHeap, 0, v6);
    if ( v8 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
    {
      v9 = v8 >> 1;
      v10 = v9 - 1;
      if ( v9 - 1 >= 8 )
      {
        v12 = *v5;
        if ( *v5 > v5 || (v11 = 0, v10 = 8, v12 + 7 < (_WORD *)v5) )
        {
          for ( i = 8; i; --i )
            *v12++ = -8531;
          goto LABEL_19;
        }
        goto LABEL_14;
      }
      if ( v9 != 1 )
      {
        v11 = 0;
        do
LABEL_14:
          *((_WORD *)*v5 + v11++) = -8531;
        while ( v11 < v10 );
      }
    }
LABEL_19:
    CoTaskMemFree(*v5);
    *v5 = 0;
  }
  v14 = (LPVOID *)((char *)this + 88);
  v15 = (const void *)*((_QWORD *)this + 11);
  if ( !v15 )
    goto LABEL_33;
  v16 = GetProcessHeap();
  v17 = HeapSize(v16, 0, v15);
  if ( v17 - 3 <= 0xFFFFFFFFFFFFFFFBuLL )
  {
    v18 = v17 >> 1;
    v19 = v18 - 1;
    if ( v18 - 1 >= 8 )
    {
      v21 = *v14;
      if ( *v14 > v14 || (v20 = 0, v19 = 8, v21 + 7 < (_WORD *)v14) )
      {
        for ( j = 8; j; --j )
          *v21++ = -8531;
        goto LABEL_32;
      }
      goto LABEL_27;
    }
    if ( v18 != 1 )
    {
      v20 = 0;
      do
LABEL_27:
        *((_WORD *)*v14 + v20++) = -8531;
      while ( v20 < v19 );
    }
  }
LABEL_32:
  CoTaskMemFree(*v14);
  *v14 = 0;
LABEL_33:
  if ( *((_BYTE *)this + 56) )
  {
    *((_BYTE *)this + 56) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  }
}

```

## disassembly

```asm
0x18001bb88  push    rbx
0x18001bb8a  push    rsi
0x18001bb8b  push    rdi
0x18001bb8c  push    r14
0x18001bb8e  push    r15
0x18001bb90  sub     rsp, 20h
0x18001bb94  mov     rsi, rcx
0x18001bb97  mov     rcx, [rcx+78h]
0x18001bb9b  test    rcx, rcx
0x18001bb9e  jz      short loc_18001BBAD
0x18001bba0  mov     rax, [rcx]
0x18001bba3  mov     rax, [rax+10h]
0x18001bba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbac  nop
0x18001bbad  mov     rcx, [rsi+70h]
0x18001bbb1  test    rcx, rcx
0x18001bbb4  jz      short loc_18001BBC3
0x18001bbb6  mov     rax, [rcx]
0x18001bbb9  mov     rax, [rax+10h]
0x18001bbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbc2  nop
0x18001bbc3  mov     rcx, [rsi+68h]
0x18001bbc7  test    rcx, rcx
0x18001bbca  jz      short loc_18001BBD9
0x18001bbcc  mov     rax, [rcx]
0x18001bbcf  mov     rax, [rax+10h]
0x18001bbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbd8  nop
0x18001bbd9  lea     rbx, [rsi+60h]
0x18001bbdd  mov     rdi, [rbx]
0x18001bbe0  mov     r14d, 8
0x18001bbe6  mov     r15d, 0DEADh
0x18001bbec  test    rdi, rdi
0x18001bbef  jz      short loc_18001BC66
0x18001bbf1  call    cs:__imp_GetProcessHeap
0x18001bbf7  mov     r8, rdi; lpMem
0x18001bbfa  xor     edx, edx; dwFlags
0x18001bbfc  mov     rcx, rax; hHeap
0x18001bbff  call    cs:__imp_HeapSize
0x18001bc05  lea     rcx, [rax-3]
0x18001bc09  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001bc0d  ja      short loc_18001BC56
0x18001bc0f  shr     rax, 1
0x18001bc12  lea     rdx, [rax-1]
0x18001bc16  cmp     rdx, r14
0x18001bc19  jnb     short loc_18001BC24
0x18001bc1b  test    rdx, rdx
0x18001bc1e  jz      short loc_18001BC56
0x18001bc20  xor     ecx, ecx
0x18001bc22  jmp     short loc_18001BC3A
0x18001bc24  mov     rdi, [rbx]
0x18001bc27  cmp     rdi, rbx
0x18001bc2a  ja      short loc_18001BC4C
0x18001bc2c  xor     ecx, ecx
0x18001bc2e  mov     rdx, r14
0x18001bc31  lea     rax, [rdi+0Eh]
0x18001bc35  cmp     rax, rbx
0x18001bc38  jb      short loc_18001BC4C
0x18001bc3a  mov     rax, [rbx]
0x18001bc3d  mov     [rax+rcx*2], r15w
0x18001bc42  inc     rcx
0x18001bc45  cmp     rcx, rdx
0x18001bc48  jb      short loc_18001BC3A
0x18001bc4a  jmp     short loc_18001BC56
0x18001bc4c  movzx   eax, r15w
0x18001bc50  mov     rcx, r14
0x18001bc53  rep stosw
0x18001bc56  mov     rcx, [rbx]; pv
0x18001bc59  call    cs:__imp_CoTaskMemFree
0x18001bc5f  mov     qword ptr [rbx], 0
0x18001bc66  lea     rbx, [rsi+58h]
0x18001bc6a  mov     rdi, [rbx]
0x18001bc6d  test    rdi, rdi
0x18001bc70  jz      short loc_18001BCE7
0x18001bc72  call    cs:__imp_GetProcessHeap
0x18001bc78  mov     r8, rdi; lpMem
0x18001bc7b  xor     edx, edx; dwFlags
0x18001bc7d  mov     rcx, rax; hHeap
0x18001bc80  call    cs:__imp_HeapSize
0x18001bc86  lea     rcx, [rax-3]
0x18001bc8a  cmp     rcx, 0FFFFFFFFFFFFFFFBh
0x18001bc8e  ja      short loc_18001BCD7
0x18001bc90  shr     rax, 1
0x18001bc93  lea     rdx, [rax-1]
0x18001bc97  cmp     rdx, r14
0x18001bc9a  jnb     short loc_18001BCA5
0x18001bc9c  test    rdx, rdx
0x18001bc9f  jz      short loc_18001BCD7
0x18001bca1  xor     ecx, ecx
0x18001bca3  jmp     short loc_18001BCBB
0x18001bca5  mov     rdi, [rbx]
0x18001bca8  cmp     rdi, rbx
0x18001bcab  ja      short loc_18001BCCD
0x18001bcad  xor     ecx, ecx
0x18001bcaf  mov     rdx, r14
0x18001bcb2  lea     rax, [rdi+0Eh]
0x18001bcb6  cmp     rax, rbx
0x18001bcb9  jb      short loc_18001BCCD
0x18001bcbb  mov     rax, [rbx]
0x18001bcbe  mov     [rax+rcx*2], r15w
0x18001bcc3  inc     rcx
0x18001bcc6  cmp     rcx, rdx
0x18001bcc9  jb      short loc_18001BCBB
0x18001bccb  jmp     short loc_18001BCD7
0x18001bccd  movzx   eax, r15w
0x18001bcd1  mov     rcx, r14
0x18001bcd4  rep stosw
0x18001bcd7  mov     rcx, [rbx]; pv
0x18001bcda  call    cs:__imp_CoTaskMemFree
0x18001bce0  mov     qword ptr [rbx], 0
0x18001bce7  lea     rcx, [rsi+10h]; lpCriticalSection
0x18001bceb  cmp     byte ptr [rcx+28h], 0
0x18001bcef  jz      short loc_18001BCFC
0x18001bcf1  mov     byte ptr [rcx+28h], 0
0x18001bcf5  call    cs:__imp_DeleteCriticalSection
0x18001bcfb  nop
0x18001bcfc  add     rsp, 20h
0x18001bd00  pop     r15
0x18001bd02  pop     r14
0x18001bd04  pop     rdi
0x18001bd05  pop     rsi
0x18001bd06  pop     rbx
0x18001bd07  retn
```
