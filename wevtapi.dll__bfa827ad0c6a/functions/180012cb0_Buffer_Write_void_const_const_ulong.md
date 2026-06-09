# Buffer::Write(void const * const,ulong)

- ea: `0x180012cb0`
- end: `0x180012eee`
- name: `?Write@Buffer@@UEAAXQEBXK@Z`
- size: `574`
- prototype: `void __fastcall(Buffer *this, const void *, unsigned int)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x1800121bc`
- `0x1800123e0`
- `0x180012420`
- `0x180017864`
- `0x180022db0`
- `0x180026e90`
- `0x1800280c0`
- `0x1800377a8`
- `0x1800381e0`

## callees

- `0x180012cb0`
- `0x180023548`
- `0x180038fa4`
- `0x180038fbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012d33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012d6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012d33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012d6d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012d41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012d41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012d7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012d7b`

## pseudocode

```c
void __fastcall Buffer::Write(Buffer *this, const void *a2, unsigned int a3)
{
  unsigned int v3; // eax
  size_t v5; // rsi
  unsigned int v7; // ecx
  unsigned int v8; // eax
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  void *v11; // rax
  void *v12; // r15
  void *v13; // rdi
  HANDLE v14; // rax
  __int128 pExceptionObject; // [rsp+20h] [rbp-48h] BYREF
  __int64 v16; // [rsp+30h] [rbp-38h]
  int v17; // [rsp+38h] [rbp-30h]
  int v18; // [rsp+3Ch] [rbp-2Ch]
  int v19; // [rsp+40h] [rbp-28h]

  v3 = *((_DWORD *)this + 4);
  v5 = a3;
  v7 = v3 + a3;
  if ( v3 + a3 < v3 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8de7935945da3ad983d1882f763b3705_Traceguids, 13);
    }
    v17 = 13;
    v18 = -1;
    v16 = 0;
    v19 = 97;
    pExceptionObject = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v8 = *((_DWORD *)this + 5);
  if ( v7 > v8 )
  {
    if ( v7 > 0x10000000 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8de7935945da3ad983d1882f763b3705_Traceguids, 13);
      }
      v17 = 13;
      v18 = -1;
      v16 = 0;
      v19 = 128;
      pExceptionObject = 0;
      throw (EvtException *)&pExceptionObject;
    }
    v9 = 2 * v8;
    if ( 2 * v8 <= v7 )
      v9 = v7 + 256;
    ProcessHeap = GetProcessHeap();
    v11 = HeapAlloc(ProcessHeap, 0, v9);
    v12 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_9f6acc06f74e36af2e5d97cacf75640c_Traceguids, 14);
      }
      v17 = 14;
      v18 = -1;
      v16 = 0;
      v19 = 17;
      pExceptionObject = 0;
      throw (EvtException *)&pExceptionObject;
    }
    memcpy_0(v11, *((const void **)this + 1), *((unsigned int *)this + 4));
    if ( *((_BYTE *)this + 24) )
    {
      v13 = (void *)*((_QWORD *)this + 1);
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v13);
    }
    *((_DWORD *)this + 5) = v9;
    *((_QWORD *)this + 1) = v12;
    *((_BYTE *)this + 24) = 1;
  }
  memcpy_0((void *)(*((_QWORD *)this + 1) + *((unsigned int *)this + 4)), a2, v5);
  *((_DWORD *)this + 4) += v5;
}

```

## disassembly

```asm
0x180012cb0  push    rbx
0x180012cb2  push    rbp
0x180012cb3  push    rsi
0x180012cb4  sub     rsp, 50h
0x180012cb8  mov     eax, [rcx+10h]
0x180012cbb  mov     rbx, rcx
0x180012cbe  mov     esi, r8d
0x180012cc1  mov     rbp, rdx
0x180012cc4  lea     ecx, [rax+rsi]
0x180012cc7  cmp     ecx, eax
0x180012cc9  jb      loc_180012D92
0x180012ccf  mov     eax, [rbx+14h]
0x180012cd2  mov     [rsp+68h+arg_0], rdi
0x180012cd7  mov     [rsp+68h+arg_8], r14
0x180012cdc  mov     [rsp+68h+arg_10], r15
0x180012ce4  cmp     ecx, eax
0x180012ce6  ja      short loc_180012D17
0x180012ce8  mov     ecx, [rbx+10h]
0x180012ceb  mov     r8, rsi; Size
0x180012cee  add     rcx, [rbx+8]; void *
0x180012cf2  mov     rdx, rbp; Src
0x180012cf5  call    memcpy_0
0x180012cfa  add     [rbx+10h], esi
0x180012cfd  mov     r14, [rsp+68h+arg_8]
0x180012d02  mov     rdi, [rsp+68h+arg_0]
0x180012d07  mov     r15, [rsp+68h+arg_10]
0x180012d0f  add     rsp, 50h
0x180012d13  pop     rsi
0x180012d14  pop     rbp
0x180012d15  pop     rbx
0x180012d16  retn
0x180012d17  cmp     ecx, 10000000h
0x180012d1d  ja      loc_180012E06
0x180012d23  lea     r14d, [rax+rax]
0x180012d27  cmp     r14d, ecx
0x180012d2a  ja      short loc_180012D33
0x180012d2c  lea     r14d, [rcx+100h]
0x180012d33  call    cs:__imp_GetProcessHeap
0x180012d39  mov     r8d, r14d; dwBytes
0x180012d3c  xor     edx, edx; dwFlags
0x180012d3e  mov     rcx, rax; hHeap
0x180012d41  call    cs:__imp_HeapAlloc
0x180012d47  mov     r15, rax
0x180012d4a  test    rax, rax
0x180012d4d  jz      loc_180012E7A
0x180012d53  mov     r8d, [rbx+10h]; Size
0x180012d57  mov     rcx, rax; void *
0x180012d5a  mov     rdx, [rbx+8]; Src
0x180012d5e  call    memcpy_0
0x180012d63  cmp     byte ptr [rbx+18h], 0
0x180012d67  jz      short loc_180012D81
0x180012d69  mov     rdi, [rbx+8]
0x180012d6d  call    cs:__imp_GetProcessHeap
0x180012d73  mov     r8, rdi; lpMem
0x180012d76  xor     edx, edx; dwFlags
0x180012d78  mov     rcx, rax; hHeap
0x180012d7b  call    cs:__imp_HeapFree
0x180012d81  mov     [rbx+14h], r14d
0x180012d85  mov     [rbx+8], r15
0x180012d89  mov     byte ptr [rbx+18h], 1
0x180012d8d  jmp     loc_180012CE8
0x180012d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d99  lea     rax, WPP_GLOBAL_Control
0x180012da0  cmp     rcx, rax
0x180012da3  jz      short loc_180012DCC
0x180012da5  test    byte ptr [rcx+1Ch], 1
0x180012da9  jz      short loc_180012DCC
0x180012dab  cmp     byte ptr [rcx+19h], 2
0x180012daf  jb      short loc_180012DCC
0x180012db1  mov     rcx, [rcx+10h]
0x180012db5  lea     r8, WPP_8de7935945da3ad983d1882f763b3705_Traceguids
0x180012dbc  mov     edx, 0Ah
0x180012dc1  mov     r9d, 0Dh
0x180012dc7  call    WPP_SF_D
0x180012dcc  xorps   xmm0, xmm0
0x180012dcf  mov     [rsp+68h+var_30], 0Dh
0x180012dd7  xor     eax, eax
0x180012dd9  mov     [rsp+68h+var_2C], 0FFFFFFFFh
0x180012de1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180012de8  mov     [rsp+68h+var_38], rax
0x180012ded  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180012df2  mov     [rsp+68h+var_28], 61h ; 'a'
0x180012dfa  movdqu  [rsp+68h+pExceptionObject], xmm0
0x180012e00  call    _CxxThrowException_0
0x180012e06  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e0d  lea     rax, WPP_GLOBAL_Control
0x180012e14  cmp     rcx, rax
0x180012e17  jz      short loc_180012E40
0x180012e19  test    byte ptr [rcx+1Ch], 1
0x180012e1d  jz      short loc_180012E40
0x180012e1f  cmp     byte ptr [rcx+19h], 2
0x180012e23  jb      short loc_180012E40
0x180012e25  mov     rcx, [rcx+10h]
0x180012e29  lea     r8, WPP_8de7935945da3ad983d1882f763b3705_Traceguids
0x180012e30  mov     edx, 0Ch
0x180012e35  mov     r9d, 0Dh
0x180012e3b  call    WPP_SF_D
0x180012e40  xorps   xmm0, xmm0
0x180012e43  mov     [rsp+68h+var_30], 0Dh
0x180012e4b  xor     eax, eax
0x180012e4d  mov     [rsp+68h+var_2C], 0FFFFFFFFh
0x180012e55  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180012e5c  mov     [rsp+68h+var_38], rax
0x180012e61  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180012e66  mov     [rsp+68h+var_28], 80h
0x180012e6e  movdqu  [rsp+68h+pExceptionObject], xmm0
0x180012e74  call    _CxxThrowException_0
0x180012e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e81  lea     rax, WPP_GLOBAL_Control
0x180012e88  cmp     rcx, rax
0x180012e8b  jz      short loc_180012EB4
0x180012e8d  test    byte ptr [rcx+1Ch], 1
0x180012e91  jz      short loc_180012EB4
0x180012e93  cmp     byte ptr [rcx+19h], 2
0x180012e97  jb      short loc_180012EB4
0x180012e99  mov     rcx, [rcx+10h]
0x180012e9d  lea     r8, WPP_9f6acc06f74e36af2e5d97cacf75640c_Traceguids
0x180012ea4  mov     edx, 0Ah
0x180012ea9  mov     r9d, 0Eh
0x180012eaf  call    WPP_SF_D
0x180012eb4  xorps   xmm0, xmm0
0x180012eb7  mov     [rsp+68h+var_30], 0Eh
0x180012ebf  xor     eax, eax
0x180012ec1  mov     [rsp+68h+var_2C], 0FFFFFFFFh
0x180012ec9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180012ed0  mov     [rsp+68h+var_38], rax
0x180012ed5  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180012eda  mov     [rsp+68h+var_28], 11h
0x180012ee2  movdqu  [rsp+68h+pExceptionObject], xmm0
0x180012ee8  call    _CxxThrowException_0
```
