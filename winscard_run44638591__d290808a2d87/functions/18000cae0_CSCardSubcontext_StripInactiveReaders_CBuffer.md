# CSCardSubcontext::StripInactiveReaders(CBuffer &)

- ea: `0x18000cae0`
- end: `0x18000cd80`
- name: `?StripInactiveReaders@CSCardSubcontext@@QEAAXAEAVCBuffer@@@Z`
- size: `672`
- prototype: `void __fastcall(CSCardSubcontext *__hidden this, struct CBuffer *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18000e400`

## callees

- `0x1800040d0`
- `0x18000bcf0`
- `0x18000bd10`
- `0x18000cae0`
- `0x18000d554`
- `0x18000d640`
- `0x18001b9b8`
- `0x18001ba04`
- `0x18002ef20`
- `0x18002ef38`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cc2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cc38`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSCardSubcontext::StripInactiveReaders(CSCardSubcontext *this, struct CBuffer *a2)
{
  unsigned __int16 *v4; // r15
  int v5; // ecx
  const unsigned __int16 *v6; // rsi
  const WCHAR *v7; // rdx
  const unsigned __int16 *v8; // rcx
  const unsigned __int16 *i; // rax
  struct CBuffer *v10; // r8
  const unsigned __int16 *v11; // rdi
  const WCHAR *v12; // rdx
  void *v13; // r14
  ulong v14; // eax
  const unsigned __int16 *String; // rax
  int *v16; // rsi
  const unsigned __int16 *v17; // rdi
  size_t v18; // rdi
  void *v19; // rsi
  void *v20; // rcx
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  int v23; // ecx
  unsigned __int16 *v24; // rdx
  int v25; // [rsp+28h] [rbp-A0h]
  int v26[2]; // [rsp+30h] [rbp-98h] BYREF
  void *Src; // [rsp+38h] [rbp-90h]
  size_t Size; // [rsp+40h] [rbp-88h]
  LPVOID lpMem; // [rsp+48h] [rbp-80h] BYREF
  ulong v30; // [rsp+50h] [rbp-78h] BYREF
  ulong pExceptionObject; // [rsp+54h] [rbp-74h] BYREF
  int v32; // [rsp+58h] [rbp-70h] BYREF
  ulong v33; // [rsp+5Ch] [rbp-6Ch] BYREF
  ulong v34; // [rsp+60h] [rbp-68h] BYREF
  const int *v35; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int16 *v36; // [rsp+70h] [rbp-58h]
  __int64 v37; // [rsp+78h] [rbp-50h]
  LPVOID v38; // [rsp+80h] [rbp-48h]

  v35 = &CBuffer::`vftable';
  v4 = 0;
  v36 = 0;
  v37 = 0;
  *(_QWORD *)v26 = &CBuffer::`vftable';
  Src = 0;
  Size = 0;
  lpMem = 0;
  v32 = 0;
  v5 = *((_DWORD *)a2 + 5);
  v6 = &WideCharStr;
  if ( v5 )
    v7 = (const WCHAR *)*((_QWORD *)a2 + 1);
  else
    v7 = &WideCharStr;
  if ( !*v7 )
  {
    v30 = -2146435026;
    throw &v30;
  }
  if ( v5 )
    v8 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  else
    v8 = &WideCharStr;
  for ( i = FirstString(v8); ; i = NextString(v11) )
  {
    v11 = i;
    if ( !i )
      break;
    if ( !(unsigned int)GetReaderInfo(*(_DWORD *)(*((_QWORD *)this + 5) + 28LL), i, v10, (const void **)&v35) )
    {
      pExceptionObject = -2146435063;
      throw &pExceptionObject;
    }
    v24 = (unsigned __int16 *)&WideCharStr;
    v4 = v36;
    if ( HIDWORD(v37) )
      v24 = v36;
    MStrAdd((struct CBuffer *)v26, v24);
  }
  v12 = &WideCharStr;
  v13 = Src;
  if ( HIDWORD(Size) )
    LODWORD(v12) = (_DWORD)Src;
  v14 = CalRpcListReaders(
          *((_QWORD *)this + 14),
          (int)v12,
          Size,
          (int)&lpMem,
          (__int64)&v32,
          v25,
          v26[0],
          (int)Src,
          Size);
  if ( v14 )
  {
    v33 = v14;
    throw &v33;
  }
  LODWORD(Size) = 0;
  try
  {
    if ( *((_DWORD *)a2 + 5) )
      v6 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
    String = FirstString(v6);
    v16 = (int *)lpMem;
    v38 = lpMem;
    while ( 1 )
    {
      v17 = String;
      if ( !String )
        break;
      v23 = *v16++;
      v38 = v16;
      if ( v23 )
      {
        MStrAdd((struct CBuffer *)v26, String);
        v13 = Src;
      }
      String = NextString(v17);
    }
    v18 = (unsigned int)Size;
    if ( *((_DWORD *)a2 + 5) >= (unsigned int)Size )
    {
      v19 = (void *)*((_QWORD *)a2 + 1);
    }
    else
    {
      v19 = operator new[]((unsigned int)Size);
      if ( !v19 )
      {
        v34 = 14;
        throw &v34;
      }
      v20 = (void *)*((_QWORD *)a2 + 1);
      if ( v20 )
        operator delete(v20);
      *((_QWORD *)a2 + 1) = v19;
      *((_DWORD *)a2 + 5) = v18;
    }
    *((_DWORD *)a2 + 4) = 0;
    if ( (_DWORD)v18 )
      memcpy_0(v19, v13, v18);
    *((_DWORD *)a2 + 4) = v18;
  }
  catch ( ... )
  {
    MIDL_user_free(lpMem);
    throw;
  }
  v21 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  *(_QWORD *)v26 = &CBuffer::`vftable';
  if ( v13 )
    operator delete(v13);
  Src = 0;
  Size = 0;
  v35 = &CBuffer::`vftable';
  if ( v4 )
    operator delete(v4);
  v36 = 0;
  v37 = 0;
}

```

## disassembly

```asm
0x18000cae0  push    rbx
0x18000cae2  push    rsi
0x18000cae3  push    rdi
0x18000cae4  push    r12
0x18000cae6  push    r13
0x18000cae8  push    r14
0x18000caea  push    r15
0x18000caec  sub     rsp, 90h
0x18000caf3  mov     rbx, rdx
0x18000caf6  mov     r13, rcx
0x18000caf9  lea     rax, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000cb00  mov     [rsp+0C8h+var_60], rax
0x18000cb05  xor     r12d, r12d
0x18000cb08  mov     r15d, r12d
0x18000cb0b  mov     [rsp+0C8h+var_58], r12
0x18000cb10  mov     [rsp+0C8h+var_50], r12
0x18000cb15  mov     qword ptr [rsp+0C8h+var_98], rax; int
0x18000cb1a  mov     [rsp+0C8h+Src], r12; int
0x18000cb1f  mov     [rsp+0C8h+Size], r12; pExceptionObject
0x18000cb24  mov     [rsp+0C8h+lpMem], r12
0x18000cb29  mov     dword ptr [rsp+0C8h+var_70], r12d
0x18000cb2e  mov     ecx, [rdx+14h]
0x18000cb31  lea     rsi, WideCharStr
0x18000cb38  test    ecx, ecx
0x18000cb3a  jz      loc_18000CD55
0x18000cb40  mov     rdx, [rdx+8]
0x18000cb44  cmp     r12w, [rdx]
0x18000cb48  jz      loc_18000CCC3
0x18000cb4e  test    ecx, ecx
0x18000cb50  jz      loc_18000CD5D
0x18000cb56  mov     rcx, [rbx+8]; unsigned __int16 *
0x18000cb5a  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000cb5f  mov     rdi, rax
0x18000cb62  test    rax, rax
0x18000cb65  jnz     loc_18000CC91
0x18000cb6b  mov     rdx, rsi
0x18000cb6e  mov     r14, [rsp+0C8h+Src]
0x18000cb73  cmp     dword ptr [rsp+0C8h+Size+4], eax
0x18000cb77  cmova   rdx, r14; int
0x18000cb7b  lea     rax, [rsp+0C8h+var_70]
0x18000cb80  mov     [rsp+0C8h+var_A8], rax; __int64
0x18000cb85  lea     r9, [rsp+0C8h+lpMem]; int
0x18000cb8a  mov     r8d, dword ptr [rsp+0C8h+Size]; int
0x18000cb8f  mov     rcx, [r13+70h]; int
0x18000cb93  call    CalRpcListReaders
0x18000cb98  test    eax, eax
0x18000cb9a  jnz     loc_18000CCDD
0x18000cba0  mov     dword ptr [rsp+0C8h+Size], r12d
0x18000cba5  cmp     [rbx+14h], eax
0x18000cba8  jbe     short loc_18000CBAE
0x18000cbaa  mov     rsi, [rbx+8]
0x18000cbae  mov     rcx, rsi; unsigned __int16 *
0x18000cbb1  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000cbb6  mov     rsi, [rsp+0C8h+lpMem]
0x18000cbbb  mov     [rsp+0C8h+var_48], rsi
0x18000cbc3  mov     rdi, rax
0x18000cbc6  test    rax, rax
0x18000cbc9  jnz     loc_18000CCF3
0x18000cbcf  mov     edi, dword ptr [rsp+0C8h+Size]
0x18000cbd3  cmp     [rbx+14h], edi
0x18000cbd6  jnb     loc_18000CD4C
0x18000cbdc  mov     ecx, edi; unsigned __int64
0x18000cbde  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000cbe3  mov     rsi, rax
0x18000cbe6  test    rax, rax
0x18000cbe9  jz      loc_18000CD65
0x18000cbef  mov     rcx, [rbx+8]; void *
0x18000cbf3  test    rcx, rcx
0x18000cbf6  jz      short loc_18000CBFD
0x18000cbf8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cbfd  mov     [rbx+8], rsi
0x18000cc01  mov     [rbx+14h], edi
0x18000cc04  xor     r13d, r13d
0x18000cc07  mov     [rbx+10h], r13d
0x18000cc0b  test    edi, edi
0x18000cc0d  jz      short loc_18000CC1D
0x18000cc0f  mov     r8, rdi; Size
0x18000cc12  mov     rdx, r14; Src
0x18000cc15  mov     rcx, rsi; void *
0x18000cc18  call    memcpy_0
0x18000cc1d  mov     [rbx+10h], edi
0x18000cc20  mov     rbx, [rsp+0C8h+lpMem]
0x18000cc25  test    rbx, rbx
0x18000cc28  jz      short loc_18000CC3F
0x18000cc2a  call    cs:__imp_GetProcessHeap
0x18000cc30  mov     rcx, rax; hHeap
0x18000cc33  mov     r8, rbx; lpMem
0x18000cc36  xor     edx, edx; dwFlags
0x18000cc38  call    cs:__imp_HeapFree
0x18000cc3e  nop
0x18000cc3f  lea     rbx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000cc46  mov     qword ptr [rsp+0C8h+var_98], rbx
0x18000cc4b  test    r14, r14
0x18000cc4e  jz      short loc_18000CC58
0x18000cc50  mov     rcx, r14; void *
0x18000cc53  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cc58  mov     [rsp+0C8h+Src], r13
0x18000cc5d  mov     [rsp+0C8h+Size], r13
0x18000cc62  mov     [rsp+0C8h+var_60], rbx
0x18000cc67  test    r15, r15
0x18000cc6a  jz      short loc_18000CC74
0x18000cc6c  mov     rcx, r15; void *
0x18000cc6f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cc74  mov     [rsp+0C8h+var_58], r13
0x18000cc79  mov     [rsp+0C8h+var_50], r13
0x18000cc7e  add     rsp, 90h
0x18000cc85  pop     r15
0x18000cc87  pop     r14
0x18000cc89  pop     r13
0x18000cc8b  pop     r12
0x18000cc8d  pop     rdi
0x18000cc8e  pop     rsi
0x18000cc8f  pop     rbx
0x18000cc90  retn
0x18000cc91  mov     rcx, [r13+28h]
0x18000cc95  lea     r9, [rsp+0C8h+var_60]; struct CBuffer *
0x18000cc9a  mov     rdx, rdi; unsigned __int16 *
0x18000cc9d  mov     ecx, [rcx+1Ch]; unsigned int
0x18000cca0  call    ?GetReaderInfo@@YAHKPEBGPEAVCBuffer@@1@Z; GetReaderInfo(ulong,ushort const *,CBuffer *,CBuffer *)
0x18000cca5  test    eax, eax
0x18000cca7  jnz     short loc_18000CD24
0x18000cca9  mov     [rsp+0C8h+pExceptionObject], 80100009h
0x18000ccb1  lea     rdx, _TI1K; pThrowInfo
0x18000ccb8  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18000ccbd  call    _CxxThrowException_0
0x18000ccc3  mov     [rsp+0C8h+var_78], 8010002Eh
0x18000cccb  lea     rdx, _TI1K; pThrowInfo
0x18000ccd2  lea     rcx, [rsp+0C8h+var_78]; pExceptionObject
0x18000ccd7  call    _CxxThrowException_0
0x18000ccdd  mov     dword ptr [rsp+0C8h+var_70+4], eax
0x18000cce1  lea     rdx, _TI1K; pThrowInfo
0x18000cce8  lea     rcx, [rsp+0C8h+var_70+4]; pExceptionObject
0x18000cced  call    _CxxThrowException_0
0x18000ccf3  mov     ecx, [rsi]
0x18000ccf5  add     rsi, 4
0x18000ccf9  mov     [rsp+0C8h+var_48], rsi
0x18000cd01  test    ecx, ecx
0x18000cd03  jz      short loc_18000CD17
0x18000cd05  mov     rdx, rdi; unsigned __int16 *
0x18000cd08  lea     rcx, [rsp+0C8h+var_98]; struct CBuffer *
0x18000cd0d  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18000cd12  mov     r14, [rsp+0C8h+Src]
0x18000cd17  mov     rcx, rdi; unsigned __int16 *
0x18000cd1a  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18000cd1f  jmp     loc_18000CBC3
0x18000cd24  mov     rdx, rsi
0x18000cd27  mov     r15, [rsp+0C8h+var_58]
0x18000cd2c  cmp     dword ptr [rsp+0C8h+var_50+4], 0
0x18000cd31  cmova   rdx, r15; unsigned __int16 *
0x18000cd35  lea     rcx, [rsp+0C8h+var_98]; struct CBuffer *
0x18000cd3a  call    ?MStrAdd@@YAKAEAVCBuffer@@PEBG@Z; MStrAdd(CBuffer &,ushort const *)
0x18000cd3f  mov     rcx, rdi; unsigned __int16 *
0x18000cd42  call    ?NextString@@YAPEBGPEBG@Z; NextString(ushort const *)
0x18000cd47  jmp     loc_18000CB5F
0x18000cd4c  mov     rsi, [rbx+8]
0x18000cd50  jmp     loc_18000CC04
0x18000cd55  mov     rdx, rsi
0x18000cd58  jmp     loc_18000CB44
0x18000cd5d  mov     rcx, rsi
0x18000cd60  jmp     loc_18000CB5A
0x18000cd65  mov     [rsp+0C8h+var_68], 0Eh
0x18000cd6d  lea     rdx, _TI1K; pThrowInfo
0x18000cd74  lea     rcx, [rsp+0C8h+var_68]; pExceptionObject
0x18000cd79  call    _CxxThrowException_0
```
