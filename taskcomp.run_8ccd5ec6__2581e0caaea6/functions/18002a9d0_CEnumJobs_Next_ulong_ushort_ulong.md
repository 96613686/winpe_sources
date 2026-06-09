# CEnumJobs::Next(ulong,ushort * * *,ulong *)

- ea: `0x18002a9d0`
- end: `0x18002ac66`
- name: `?Next@CEnumJobs@@UEAAJKPEAPEAPEAGPEAK@Z`
- size: `662`
- prototype: `__int64 __fastcall(CEnumJobs *__hidden this, unsigned int, unsigned __int16 ***, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180007988`
- `0x180008c66`
- `0x18002a6d4`
- `0x18002a9d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aacf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ab84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002aacf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ab84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ac2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aa58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aaa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002abac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aa58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002aaa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002ab4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002abac`

## pseudocode

```c
__int64 __fastcall CEnumJobs::Next(CEnumJobs *this, unsigned int a2, LPVOID *a3, unsigned int *a4)
{
  CEnumJobs *v7; // r12
  __int64 result; // rax
  unsigned int v9; // esi
  unsigned __int16 **v10; // rax
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // rbp
  __int64 v13; // rax
  _QWORD *v14; // rbx
  unsigned __int64 v15; // r13
  _WORD *v16; // rcx
  unsigned int v17; // ebx
  __int64 v18; // rbp
  int Next; // eax
  unsigned __int16 *v20; // r12
  unsigned __int16 **v21; // r13
  unsigned __int16 **v22; // rax
  __int64 v23; // rax
  unsigned __int64 v24; // r13
  LPVOID v25; // rax
  void *v26; // rdx
  unsigned __int16 *v27; // rcx
  LPVOID *v28; // r15
  int i; // ebx
  void *Block[11]; // [rsp+20h] [rbp-58h] BYREF

  v7 = this;
  if ( !a2 || a2 > 1 && !a4 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  if ( *((_DWORD *)this + 149) )
  {
    if ( a4 )
      *a4 = 0;
    return 1;
  }
  Block[0] = 0;
  result = CEnumJobs::GetNext(this, (unsigned __int16 **)Block);
  v9 = result;
  if ( (_DWORD)result )
  {
    if ( a4 )
      *a4 = 0;
    *a3 = 0;
    return result;
  }
  v10 = (unsigned __int16 **)CoTaskMemAlloc(8u);
  *a3 = v10;
  if ( !v10 )
  {
    if ( a4 )
      *a4 = 0;
    v11 = (unsigned __int16 *)Block[0];
LABEL_17:
    operator delete(v11);
    return 2147942414LL;
  }
  v12 = (unsigned __int16 *)Block[0];
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)Block[0] + v13) );
  v14 = *a3;
  v15 = v13 + 1;
  *v14 = CoTaskMemAlloc(2 * (v13 + 1));
  v16 = *(_WORD **)*a3;
  if ( !v16 )
  {
    if ( a4 )
      *a4 = 0;
    CoTaskMemFree(*a3);
    v11 = v12;
    *a3 = 0;
    goto LABEL_17;
  }
  *v16 = 0;
  StringCchCopyW(*(unsigned __int16 **)*a3, v15, v12);
  operator delete(v12);
  if ( a2 == 1 )
  {
    if ( a4 )
      *a4 = 1;
    return 0;
  }
  else
  {
    v17 = 1;
    while ( 1 )
    {
      v18 = v17++;
      if ( v17 > a2 )
        goto LABEL_42;
      Next = CEnumJobs::GetNext(v7, (unsigned __int16 **)Block);
      v20 = (unsigned __int16 *)Block[0];
      v9 = Next;
      if ( Next )
        break;
      v21 = (unsigned __int16 **)*a3;
      v22 = (unsigned __int16 **)CoTaskMemAlloc(8LL * v17);
      *a3 = v22;
      if ( !v22 )
      {
        *a3 = v21;
LABEL_37:
        v9 = -2147024882;
        goto LABEL_39;
      }
      Block[0] = (void *)(8 * v18);
      memcpy_0(v22, v21, 8 * v18);
      CoTaskMemFree(v21);
      v23 = -1;
      do
        ++v23;
      while ( v20[v23] );
      v24 = v23 + 1;
      v25 = CoTaskMemAlloc(2 * (v23 + 1));
      v26 = Block[0];
      *(_QWORD *)((char *)Block[0] + (unsigned __int64)*a3) = v25;
      v27 = *(unsigned __int16 **)((char *)*a3 + (_QWORD)v26);
      if ( !v27 )
        goto LABEL_37;
      StringCchCopyW(v27, v24, v20);
      operator delete(v20);
      v7 = this;
      Block[0] = 0;
    }
    if ( Next >= 0 )
    {
LABEL_42:
      *a4 = v18;
      return v9;
    }
LABEL_39:
    v28 = (LPVOID *)*a3;
    for ( i = 0; i < (int)v18; ++i )
      CoTaskMemFree(v28[i]);
    CoTaskMemFree(v28);
    operator delete(v20);
    *a4 = 0;
    *a3 = 0;
    return v9;
  }
}

```

## disassembly

```asm
0x18002a9d0  mov     [rsp+arg_0], rcx
0x18002a9d5  push    rbx
0x18002a9d6  push    rbp
0x18002a9d7  push    rsi
0x18002a9d8  push    rdi
0x18002a9d9  push    r12
0x18002a9db  push    r13
0x18002a9dd  push    r14
0x18002a9df  push    r15
0x18002a9e1  sub     rsp, 38h
0x18002a9e5  xor     ebx, ebx
0x18002a9e7  mov     rdi, r9
0x18002a9ea  mov     r14, r8
0x18002a9ed  mov     r15d, edx
0x18002a9f0  mov     r12, rcx
0x18002a9f3  test    edx, edx
0x18002a9f5  jz      loc_18002AC4F
0x18002a9fb  cmp     edx, 1
0x18002a9fe  jbe     short loc_18002AA09
0x18002aa00  test    r9, r9
0x18002aa03  jz      loc_18002AC4F
0x18002aa09  test    r14, r14
0x18002aa0c  jz      loc_18002AC4F
0x18002aa12  mov     [r8], rbx
0x18002aa15  cmp     [rcx+254h], ebx
0x18002aa1b  jz      short loc_18002AA2F
0x18002aa1d  test    rdi, rdi
0x18002aa20  jz      short loc_18002AA25
0x18002aa22  mov     [r9], ebx
0x18002aa25  mov     eax, 1
0x18002aa2a  jmp     loc_18002AC54
0x18002aa2f  lea     rdx, [rsp+78h+Block]; unsigned __int16 **
0x18002aa34  mov     [rsp+78h+Block], rbx
0x18002aa39  call    ?GetNext@CEnumJobs@@AEAAJPEAPEAG@Z; CEnumJobs::GetNext(ushort * *)
0x18002aa3e  mov     esi, eax
0x18002aa40  test    eax, eax
0x18002aa42  jz      short loc_18002AA53
0x18002aa44  test    rdi, rdi
0x18002aa47  jz      short loc_18002AA4B
0x18002aa49  mov     [rdi], ebx
0x18002aa4b  mov     [r14], rbx
0x18002aa4e  jmp     loc_18002AC54
0x18002aa53  mov     ecx, 8; cb
0x18002aa58  call    cs:__imp_CoTaskMemAlloc
0x18002aa5f  nop     dword ptr [rax+rax+00h]
0x18002aa64  mov     [r14], rax
0x18002aa67  test    rax, rax
0x18002aa6a  jnz     short loc_18002AA87
0x18002aa6c  test    rdi, rdi
0x18002aa6f  jz      short loc_18002AA73
0x18002aa71  mov     [rdi], ebx
0x18002aa73  mov     rcx, [rsp+78h+Block]; Block
0x18002aa78  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aa7d  mov     eax, 8007000Eh
0x18002aa82  jmp     loc_18002AC54
0x18002aa87  mov     rbp, [rsp+78h+Block]
0x18002aa8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002aa90  inc     rax
0x18002aa93  cmp     [rbp+rax*2+0], bx
0x18002aa98  jnz     short loc_18002AA90
0x18002aa9a  mov     rbx, [r14]
0x18002aa9d  lea     r13, [rax+1]
0x18002aaa1  lea     rcx, ds:0[r13*2]; cb
0x18002aaa9  call    cs:__imp_CoTaskMemAlloc
0x18002aab0  nop     dword ptr [rax+rax+00h]
0x18002aab5  mov     [rbx], rax
0x18002aab8  xor     ebx, ebx
0x18002aaba  mov     rax, [r14]
0x18002aabd  mov     rcx, [rax]
0x18002aac0  test    rcx, rcx
0x18002aac3  jnz     short loc_18002AAE3
0x18002aac5  test    rdi, rdi
0x18002aac8  jz      short loc_18002AACC
0x18002aaca  mov     [rdi], ebx
0x18002aacc  mov     rcx, [r14]; pv
0x18002aacf  call    cs:__imp_CoTaskMemFree
0x18002aad6  nop     dword ptr [rax+rax+00h]
0x18002aadb  mov     rcx, rbp
0x18002aade  mov     [r14], rbx
0x18002aae1  jmp     short loc_18002AA78
0x18002aae3  mov     [rcx], bx
0x18002aae6  mov     r8, rbp; unsigned __int16 *
0x18002aae9  mov     rcx, [r14]
0x18002aaec  mov     rdx, r13; unsigned __int64
0x18002aaef  mov     rcx, [rcx]; unsigned __int16 *
0x18002aaf2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002aaf7  mov     rcx, rbp; Block
0x18002aafa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002aaff  cmp     r15d, 1
0x18002ab03  jnz     short loc_18002AB14
0x18002ab05  test    rdi, rdi
0x18002ab08  jz      short loc_18002AB0D
0x18002ab0a  mov     [rdi], r15d
0x18002ab0d  xor     eax, eax
0x18002ab0f  jmp     loc_18002AC54
0x18002ab14  mov     ebx, 1
0x18002ab19  xor     r13d, r13d
0x18002ab1c  mov     ebp, ebx
0x18002ab1e  inc     ebx
0x18002ab20  cmp     ebx, r15d
0x18002ab23  ja      loc_18002AC49
0x18002ab29  lea     rdx, [rsp+78h+Block]; unsigned __int16 **
0x18002ab2e  mov     rcx, r12; this
0x18002ab31  call    ?GetNext@CEnumJobs@@AEAAJPEAPEAG@Z; CEnumJobs::GetNext(ushort * *)
0x18002ab36  mov     r12, [rsp+78h+Block]
0x18002ab3b  mov     esi, eax
0x18002ab3d  test    eax, eax
0x18002ab3f  jnz     loc_18002AC05
0x18002ab45  mov     r13, [r14]
0x18002ab48  mov     ecx, ebx
0x18002ab4a  shl     rcx, 3; cb
0x18002ab4e  call    cs:__imp_CoTaskMemAlloc
0x18002ab55  nop     dword ptr [rax+rax+00h]
0x18002ab5a  mov     [r14], rax
0x18002ab5d  test    rax, rax
0x18002ab60  jz      loc_18002ABF8
0x18002ab66  lea     rcx, ds:0[rbp*8]
0x18002ab6e  mov     rdx, r13; Src
0x18002ab71  mov     [rsp+78h+Block], rcx
0x18002ab76  mov     r8, rcx; Size
0x18002ab79  mov     rcx, rax; void *
0x18002ab7c  call    memcpy_0
0x18002ab81  mov     rcx, r13; pv
0x18002ab84  call    cs:__imp_CoTaskMemFree
0x18002ab8b  nop     dword ptr [rax+rax+00h]
0x18002ab90  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ab94  xor     ecx, ecx
0x18002ab96  inc     rax
0x18002ab99  cmp     [r12+rax*2], cx
0x18002ab9e  jnz     short loc_18002AB96
0x18002aba0  lea     r13, [rax+1]
0x18002aba4  lea     rcx, ds:0[r13*2]; cb
0x18002abac  call    cs:__imp_CoTaskMemAlloc
0x18002abb3  nop     dword ptr [rax+rax+00h]
0x18002abb8  mov     rcx, [r14]
0x18002abbb  mov     rdx, [rsp+78h+Block]
0x18002abc0  mov     [rdx+rcx], rax
0x18002abc4  mov     rax, [r14]
0x18002abc7  mov     rcx, [rdx+rax]; unsigned __int16 *
0x18002abcb  test    rcx, rcx
0x18002abce  jz      short loc_18002ABFB
0x18002abd0  mov     r8, r12; unsigned __int16 *
0x18002abd3  mov     rdx, r13; unsigned __int64
0x18002abd6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002abdb  mov     rcx, r12; Block
0x18002abde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002abe3  mov     r12, [rsp+78h+arg_0]
0x18002abeb  xor     r13d, r13d
0x18002abee  mov     [rsp+78h+Block], r13
0x18002abf3  jmp     loc_18002AB1C
0x18002abf8  mov     [r14], r13
0x18002abfb  mov     esi, 8007000Eh
0x18002ac00  xor     r13d, r13d
0x18002ac03  jmp     short loc_18002AC07
0x18002ac05  jns     short loc_18002AC49
0x18002ac07  mov     r15, [r14]
0x18002ac0a  mov     ebx, r13d
0x18002ac0d  test    ebp, ebp
0x18002ac0f  jle     short loc_18002AC2A
0x18002ac11  movsxd  rcx, ebx
0x18002ac14  mov     rcx, [r15+rcx*8]; pv
0x18002ac18  call    cs:__imp_CoTaskMemFree
0x18002ac1f  nop     dword ptr [rax+rax+00h]
0x18002ac24  inc     ebx
0x18002ac26  cmp     ebx, ebp
0x18002ac28  jl      short loc_18002AC11
0x18002ac2a  mov     rcx, r15; pv
0x18002ac2d  call    cs:__imp_CoTaskMemFree
0x18002ac34  nop     dword ptr [rax+rax+00h]
0x18002ac39  mov     rcx, r12; Block
0x18002ac3c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002ac41  mov     [rdi], r13d
0x18002ac44  mov     [r14], r13
0x18002ac47  jmp     short loc_18002AC4B
0x18002ac49  mov     [rdi], ebp
0x18002ac4b  mov     eax, esi
0x18002ac4d  jmp     short loc_18002AC54
0x18002ac4f  mov     eax, 80070057h
0x18002ac54  add     rsp, 38h
0x18002ac58  pop     r15
0x18002ac5a  pop     r14
0x18002ac5c  pop     r13
0x18002ac5e  pop     r12
0x18002ac60  pop     rdi
0x18002ac61  pop     rsi
0x18002ac62  pop     rbp
0x18002ac63  pop     rbx
0x18002ac64  retn
```
