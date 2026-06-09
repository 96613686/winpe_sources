# EncodingStream::Read(void *,ulong,ulong *)

- ea: `0x18000a2b0`
- end: `0x18000a6ed`
- name: `?Read@EncodingStream@@UEAAJPEAXKPEAK@Z`
- size: `1085`
- prototype: `__int64 __fastcall(EncodingStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a2b0`
- `0x18000a700`
- `0x18000c000`
- `0x1800533b8`
- `0x180067b94`
- `0x18006a0dd`
- `0x18006a0e9`
- `0x18006a110`
- `0x18006b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a550`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a550`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a594`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a594`

## string_xrefs

- `0x18000a3b6`: `SXS.DLL: XML parsing failed due to memory in-page error\n`
- `0x18000a616`: `SXS.DLL: Read %lu bytes from XML stream; HRESULT returned = 0x%08lx\n`
- `0x18000a6d2`: `SXS.DLL: XML Parser found incomplete encoding\n`

## pseudocode

```c
__int64 __fastcall EncodingStream::Read(EncodingStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int *v4; // r13
  unsigned int v6; // r12d
  unsigned int v7; // ecx
  unsigned int *v8; // rsi
  int v9; // eax
  unsigned int v10; // edi
  int *v11; // r14
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // r10
  __int64 v15; // rdx
  int v16; // r13d
  __int64 result; // rax
  unsigned int v18; // ecx
  unsigned int v19; // r8d
  __int64 (__fastcall *v20)(char *, _QWORD, _QWORD, unsigned int *, void *, unsigned int *); // r10
  int v21; // eax
  unsigned int v22; // ecx
  void *v23; // r15
  __int64 v24; // rax
  void *v25; // r8
  unsigned int v26; // ecx
  const unsigned __int16 *v27; // r9
  unsigned int v28; // edx
  unsigned int v29; // [rsp+40h] [rbp-A8h]
  unsigned __int64 v31; // [rsp+50h] [rbp-98h]
  __int64 v32; // [rsp+58h] [rbp-90h]
  unsigned int v34; // [rsp+90h] [rbp-58h] BYREF
  unsigned int v35; // [rsp+94h] [rbp-54h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-50h] BYREF

  v4 = a4;
  v6 = 0;
  v7 = 0;
  v34 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = (unsigned int *)((char *)this + 48);
  v9 = *((_DWORD *)this + 12);
  if ( !v9 && *((_BYTE *)this + 82) )
    return 0;
  v10 = a3 >> 1;
  v11 = (int *)((char *)this + 44);
  v12 = *((unsigned int *)this + 11);
  v13 = v9 - v12;
  *v8 = v13;
  if ( *((_DWORD *)this + 10) < a3 >> 1 )
  {
    v23 = HeapAlloc(g_hHeap, 0, v10);
    if ( !v23 )
      return 2147942414LL;
    v24 = *((_QWORD *)this + 4);
    if ( v24 )
    {
      memcpy_0(v23, (const void *)(v24 + (unsigned int)*v11), *v8);
      v25 = (void *)*((_QWORD *)this + 4);
      if ( v25 )
        HeapFree(g_hHeap, 0, v25);
    }
    *((_QWORD *)this + 4) = v23;
    *((_DWORD *)this + 10) = v10;
    goto LABEL_39;
  }
  if ( (_DWORD)v12 && v13 )
  {
    memmove_0(*((void **)this + 4), (const void *)(*((_QWORD *)this + 4) + v12), v13);
LABEL_39:
    v7 = v34;
  }
  *((_DWORD *)this + 13) += *v11;
  *v11 = 0;
  v14 = *((_QWORD *)this + 9);
  if ( v14 && *((_BYTE *)this + 84) )
  {
    v15 = *v8;
    if ( v10 <= (unsigned int)v15 )
      goto LABEL_18;
    v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(*(_QWORD *)v14 + 24LL))(
            *((_QWORD *)this + 9),
            *((_QWORD *)this + 4) + v15,
            v10 - (unsigned int)v15,
            &v34);
    if ( FusionpDbgWouldPrintAtFilterLevel(0x81000000) )
    {
      FusionpDbgPrintEx(0x81000000, "SXS.DLL: Read %lu bytes from XML stream; HRESULT returned = 0x%08lx\n", v34, v16);
      v7 = v34;
      if ( !v34 )
        goto LABEL_12;
      v31 = v34;
      v29 = *v8;
      v32 = *((_QWORD *)this + 4);
      if ( FusionpDbgWouldPrintAtFilterLevel(0x81000000) )
        FusionppDbgPrintBlob(v26, (void *)(v32 + v29), v31, v27);
    }
    v7 = v34;
LABEL_12:
    if ( v16 == -2147483638 && v7 )
    {
      v16 = 0;
    }
    else if ( v16 < 0 )
    {
      return (unsigned int)v16;
    }
    LODWORD(v15) = *v8;
    if ( *v8 )
    {
LABEL_17:
      v4 = a4;
      goto LABEL_18;
    }
    if ( v7 )
    {
      LODWORD(v15) = 0;
      goto LABEL_17;
    }
    *((_BYTE *)this + 82) = 1;
    return (unsigned int)v16;
  }
  LODWORD(v15) = *v8;
  if ( !*v8 )
  {
    v28 = 1;
    if ( !*((_BYTE *)this + 81) )
      return (unsigned int)-2147483638;
    return v28;
  }
LABEL_18:
  v18 = v15 + v7;
  v19 = -1;
  if ( v18 >= (unsigned int)v15 )
    v19 = v18;
  result = v18 < (unsigned int)v15 ? 0x80070216 : 0;
  *v8 = v19;
  if ( v18 >= (unsigned int)v15 )
  {
    v35 = v19;
    v36 = v10;
    if ( v19 > v10 )
      v35 = v10;
    v20 = (__int64 (__fastcall *)(char *, _QWORD, _QWORD, unsigned int *, void *, unsigned int *))*((_QWORD *)this + 7);
    if ( v20 )
      goto LABEL_27;
    result = EncodingStream::autoDetect(this);
    if ( (int)result < 0 )
      return result;
    v20 = (__int64 (__fastcall *)(char *, _QWORD, _QWORD, unsigned int *, void *, unsigned int *))*((_QWORD *)this + 7);
    if ( v20 )
    {
      v21 = *v11;
      v35 -= *v11;
      *((_DWORD *)this + 13) -= v21;
LABEL_27:
      result = v20(
                 (char *)this + 88,
                 *((unsigned int *)this + 4),
                 *((_QWORD *)this + 4) + (unsigned int)*v11,
                 &v35,
                 a2,
                 &v36);
      if ( !(_DWORD)result )
      {
        if ( v35 || v34 || !*((_QWORD *)this + 9) && !*((_BYTE *)this + 81) )
        {
          *v11 += v35;
          v22 = v36;
          if ( v4 )
            *v4 = 2 * v36;
          if ( !v22 )
            return (unsigned int)-2147483638;
          return v6;
        }
        else
        {
          FusionpDbgPrintEx(0xC0000000, "SXS.DLL: XML Parser found incomplete encoding\n");
          return 3222070548LL;
        }
      }
      return result;
    }
    result = 1;
    if ( !*((_BYTE *)this + 81) )
      return 2147483658LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000a2b0  push    rbx
0x18000a2b2  push    rsi
0x18000a2b3  push    rdi
0x18000a2b4  push    r12
0x18000a2b6  push    r13
0x18000a2b8  push    r14
0x18000a2ba  push    r15
0x18000a2bc  sub     rsp, 0B0h
0x18000a2c3  mov     rax, cs:__security_cookie
0x18000a2ca  xor     rax, rsp
0x18000a2cd  mov     [rsp+0E8h+var_48], rax
0x18000a2d5  mov     r13, r9
0x18000a2d8  mov     [rsp+0E8h+var_A0], r9
0x18000a2dd  mov     edi, r8d
0x18000a2e0  mov     [rsp+0E8h+var_88], rdx
0x18000a2e5  mov     rbx, rcx
0x18000a2e8  mov     [rsp+0E8h+var_80], rcx
0x18000a2ed  mov     [rsp+0E8h+var_78], rdx
0x18000a2f2  mov     [rsp+0E8h+var_70], r9
0x18000a2f7  xor     r12d, r12d
0x18000a2fa  mov     ecx, r12d
0x18000a2fd  mov     [rsp+0E8h+var_58], ecx
0x18000a304  test    r9, r9
0x18000a307  jz      short loc_18000A30C
0x18000a309  mov     [r9], r12d
0x18000a30c  lea     rsi, [rbx+30h]
0x18000a310  mov     [rsp+0E8h+var_68], rsi
0x18000a318  mov     eax, [rsi]
0x18000a31a  test    eax, eax
0x18000a31c  jnz     short loc_18000A327
0x18000a31e  cmp     [rbx+52h], cl
0x18000a321  jnz     loc_18000A5FA
0x18000a327  shr     edi, 1
0x18000a329  mov     [rsp+0E8h+var_A8], edi
0x18000a32d  lea     r14, [rbx+2Ch]
0x18000a331  mov     [rsp+0E8h+var_98], r14
0x18000a336  mov     edx, [r14]
0x18000a339  sub     eax, edx
0x18000a33b  mov     [rsi], eax
0x18000a33d  cmp     [rbx+28h], edi
0x18000a340  jb      loc_18000A544
0x18000a346  test    edx, edx
0x18000a348  jnz     loc_18000A5E1
0x18000a34e  lea     r15, [rbx+34h]
0x18000a352  mov     [rsp+0E8h+var_90], r15
0x18000a357  mov     eax, [r14]
0x18000a35a  add     [r15], eax
0x18000a35d  mov     [r14], r12d
0x18000a360  lea     rax, [rbx+48h]
0x18000a364  mov     [rsp+0E8h+var_60], rax
0x18000a36c  mov     r10, [rax]
0x18000a36f  test    r10, r10
0x18000a372  jz      loc_18000A674
0x18000a378  cmp     [rbx+54h], r12b
0x18000a37c  jz      loc_18000A674
0x18000a382  mov     edx, [rsi]
0x18000a384  cmp     edi, edx
0x18000a386  jbe     loc_18000A468
0x18000a38c  mov     rax, [r10]
0x18000a38f  mov     r8d, edi
0x18000a392  sub     r8d, edx
0x18000a395  add     rdx, [rbx+20h]
0x18000a399  lea     r9, [rsp+0E8h+var_58]
0x18000a3a1  mov     rcx, r10
0x18000a3a4  mov     rax, [rax+18h]
0x18000a3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ad  mov     r13d, eax
0x18000a3b0  mov     [rsp+0E8h+var_A4], eax
0x18000a3b4  jmp     short loc_18000A404
0x18000a3b6  lea     rdx, aSxsDllXmlParsi; "SXS.DLL: XML parsing failed due to memo"...
0x18000a3bd  mov     ecx, 0C0000000h; unsigned int
0x18000a3c2  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000a3c7  mov     r13d, 800703E7h
0x18000a3cd  mov     [rsp+0E8h+var_A4], r13d
0x18000a3d2  xor     r12d, r12d
0x18000a3d5  mov     rbx, [rsp+0E8h+var_80]
0x18000a3da  mov     rax, [rsp+0E8h+var_78]
0x18000a3df  mov     [rsp+0E8h+var_88], rax
0x18000a3e4  mov     rax, [rsp+0E8h+var_70]
0x18000a3e9  mov     [rsp+0E8h+var_A0], rax
0x18000a3ee  mov     rsi, [rsp+0E8h+var_68]
0x18000a3f6  mov     edi, [rsp+0E8h+var_A8]
0x18000a3fa  mov     r14, [rsp+0E8h+var_98]
0x18000a3ff  mov     r15, [rsp+0E8h+var_90]
0x18000a404  mov     ecx, 81000000h; unsigned int
0x18000a409  call    ?FusionpDbgWouldPrintAtFilterLevel@@YA_NK@Z; FusionpDbgWouldPrintAtFilterLevel(ulong)
0x18000a40e  test    al, al
0x18000a410  jnz     loc_18000A60B
0x18000a416  mov     ecx, [rsp+0E8h+var_58]
0x18000a41d  cmp     r13d, 8000000Ah
0x18000a424  jz      loc_18000A5CC
0x18000a42a  test    r13d, r13d
0x18000a42d  jns     short loc_18000A459
0x18000a42f  mov     eax, r13d
0x18000a432  mov     rcx, [rsp+0E8h+var_48]
0x18000a43a  xor     rcx, rsp; StackCookie
0x18000a43d  call    __security_check_cookie
0x18000a442  add     rsp, 0B0h
0x18000a449  pop     r15
0x18000a44b  pop     r14
0x18000a44d  pop     r13
0x18000a44f  pop     r12
0x18000a451  pop     rdi
0x18000a452  pop     rsi
0x18000a453  pop     rbx
0x18000a454  retn
0x18000a456  mov     r13d, r12d
0x18000a459  mov     edx, [rsi]
0x18000a45b  test    edx, edx
0x18000a45d  jz      loc_18000A5B3
0x18000a463  mov     r13, [rsp+0E8h+var_A0]
0x18000a468  add     ecx, edx
0x18000a46a  mov     r8d, 0FFFFFFFFh
0x18000a470  cmp     ecx, edx
0x18000a472  cmovnb  r8d, ecx
0x18000a476  sbb     eax, eax
0x18000a478  and     eax, 80070216h
0x18000a47d  mov     [rsi], r8d
0x18000a480  cmp     ecx, edx
0x18000a482  jb      short loc_18000A432
0x18000a484  mov     [rsp+0E8h+var_54], r8d
0x18000a48c  mov     [rsp+0E8h+var_50], edi
0x18000a493  cmp     r8d, edi
0x18000a496  jbe     short loc_18000A49F
0x18000a498  mov     [rsp+0E8h+var_54], edi
0x18000a49f  mov     r10, [rbx+38h]
0x18000a4a3  test    r10, r10
0x18000a4a6  jnz     short loc_18000A4D2
0x18000a4a8  mov     rcx, rbx; this
0x18000a4ab  call    ?autoDetect@EncodingStream@@AEAAJXZ; EncodingStream::autoDetect(void)
0x18000a4b0  test    eax, eax
0x18000a4b2  js      loc_18000A432
0x18000a4b8  mov     r10, [rbx+38h]
0x18000a4bc  test    r10, r10
0x18000a4bf  jz      loc_18000A696
0x18000a4c5  mov     eax, [r14]
0x18000a4c8  sub     [rsp+0E8h+var_54], eax
0x18000a4cf  sub     [r15], eax
0x18000a4d2  mov     r8d, [r14]
0x18000a4d5  add     r8, [rbx+20h]
0x18000a4d9  lea     rcx, [rbx+58h]
0x18000a4dd  lea     rax, [rsp+0E8h+var_50]
0x18000a4e5  mov     [rsp+0E8h+var_C0], rax
0x18000a4ea  mov     rax, [rsp+0E8h+var_88]
0x18000a4ef  mov     [rsp+0E8h+var_C8], rax
0x18000a4f4  lea     r9, [rsp+0E8h+var_54]
0x18000a4fc  mov     edx, [rbx+10h]
0x18000a4ff  mov     rax, r10
0x18000a502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a507  test    eax, eax
0x18000a509  jnz     loc_18000A432
0x18000a50f  mov     ecx, [rsp+0E8h+var_54]
0x18000a516  test    ecx, ecx
0x18000a518  jz      loc_18000A6AC
0x18000a51e  add     [r14], ecx
0x18000a521  mov     ecx, [rsp+0E8h+var_50]
0x18000a528  test    r13, r13
0x18000a52b  jnz     loc_18000A5C0
0x18000a531  test    ecx, ecx
0x18000a533  mov     ecx, 8000000Ah
0x18000a538  cmovz   r12d, ecx
0x18000a53c  mov     eax, r12d
0x18000a53f  jmp     loc_18000A432
0x18000a544  mov     r8d, edi; dwBytes
0x18000a547  xor     edx, edx; dwFlags
0x18000a549  mov     rcx, cs:g_hHeap; hHeap
0x18000a550  call    cs:__imp_HeapAlloc
0x18000a557  nop     dword ptr [rax+rax+00h]
0x18000a55c  mov     r15, rax
0x18000a55f  test    rax, rax
0x18000a562  jz      loc_18000A601
0x18000a568  mov     rax, [rbx+20h]
0x18000a56c  test    rax, rax
0x18000a56f  jz      short loc_18000A5A0
0x18000a571  mov     r8d, [rsi]; Size
0x18000a574  mov     edx, [r14]
0x18000a577  add     rdx, rax; Src
0x18000a57a  mov     rcx, r15; void *
0x18000a57d  call    memcpy_0
0x18000a582  mov     r8, [rbx+20h]; lpMem
0x18000a586  test    r8, r8
0x18000a589  jz      short loc_18000A5A0
0x18000a58b  xor     edx, edx; dwFlags
0x18000a58d  mov     rcx, cs:g_hHeap; hHeap
0x18000a594  call    cs:__imp_HeapFree
0x18000a59b  nop     dword ptr [rax+rax+00h]
0x18000a5a0  mov     [rbx+20h], r15
0x18000a5a4  mov     [rbx+28h], edi
0x18000a5a7  mov     ecx, [rsp+0E8h+var_58]
0x18000a5ae  jmp     loc_18000A34E
0x18000a5b3  test    ecx, ecx
0x18000a5b5  jnz     short loc_18000A5D9
0x18000a5b7  mov     byte ptr [rbx+52h], 1
0x18000a5bb  jmp     loc_18000A42F
0x18000a5c0  lea     eax, [rcx+rcx]
0x18000a5c3  mov     [r13+0], eax
0x18000a5c7  jmp     loc_18000A531
0x18000a5cc  test    ecx, ecx
0x18000a5ce  jz      loc_18000A42A
0x18000a5d4  jmp     loc_18000A456
0x18000a5d9  mov     edx, r12d
0x18000a5dc  jmp     loc_18000A463
0x18000a5e1  test    eax, eax
0x18000a5e3  jz      loc_18000A34E
0x18000a5e9  mov     rcx, [rbx+20h]; void *
0x18000a5ed  mov     r8d, eax; Size
0x18000a5f0  add     rdx, rcx; Src
0x18000a5f3  call    memmove_0
0x18000a5f8  jmp     short loc_18000A5A7
0x18000a5fa  xor     eax, eax
0x18000a5fc  jmp     loc_18000A432
0x18000a601  mov     eax, 8007000Eh
0x18000a606  jmp     loc_18000A432
0x18000a60b  mov     r9d, r13d
0x18000a60e  mov     r8d, [rsp+0E8h+var_58]
0x18000a616  lea     rdx, aSxsDllReadLuBy; "SXS.DLL: Read %lu bytes from XML stream"...
0x18000a61d  mov     ecx, 81000000h; unsigned int
0x18000a622  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000a627  mov     ecx, [rsp+0E8h+var_58]
0x18000a62e  test    ecx, ecx
0x18000a630  jz      loc_18000A41D
0x18000a636  mov     [rsp+0E8h+var_98], rcx
0x18000a63b  mov     eax, [rsi]
0x18000a63d  mov     [rsp+0E8h+var_A8], eax
0x18000a641  mov     rax, [rbx+20h]
0x18000a645  mov     [rsp+0E8h+var_90], rax
0x18000a64a  mov     ecx, 81000000h; unsigned int
0x18000a64f  call    ?FusionpDbgWouldPrintAtFilterLevel@@YA_NK@Z; FusionpDbgWouldPrintAtFilterLevel(ulong)
0x18000a654  test    al, al
0x18000a656  jz      loc_18000A416
0x18000a65c  mov     edx, [rsp+0E8h+var_A8]
0x18000a660  add     rdx, [rsp+0E8h+var_90]; void *
0x18000a665  mov     r8, [rsp+0E8h+var_98]; unsigned __int64
0x18000a66a  call    ?FusionppDbgPrintBlob@@YAXKPEAX_KPEBG@Z; FusionppDbgPrintBlob(ulong,void *,unsigned __int64,ushort const *)
0x18000a66f  jmp     loc_18000A416
0x18000a674  mov     edx, [rsi]
0x18000a676  test    edx, edx
0x18000a678  jnz     loc_18000A468
0x18000a67e  mov     edx, 1
0x18000a683  mov     eax, 8000000Ah
0x18000a688  cmp     [rbx+51h], r12b
0x18000a68c  cmovz   edx, eax
0x18000a68f  mov     eax, edx
0x18000a691  jmp     loc_18000A432
0x18000a696  mov     eax, 1
0x18000a69b  cmp     byte ptr [rbx+51h], 0
0x18000a69f  mov     ecx, 8000000Ah
0x18000a6a4  cmovz   eax, ecx
0x18000a6a7  jmp     loc_18000A432
0x18000a6ac  cmp     [rsp+0E8h+var_58], 0
0x18000a6b4  jnz     loc_18000A51E
0x18000a6ba  mov     rax, [rsp+0E8h+var_60]
0x18000a6c2  cmp     qword ptr [rax], 0
0x18000a6c6  jnz     short loc_18000A6D2
0x18000a6c8  cmp     byte ptr [rbx+51h], 0
0x18000a6cc  jz      loc_18000A51E
0x18000a6d2  lea     rdx, aSxsDllXmlParse_9; "SXS.DLL: XML Parser found incomplete en"...
0x18000a6d9  mov     ecx, 0C0000000h; unsigned int
0x18000a6de  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x18000a6e3  mov     eax, 0C00CE514h
0x18000a6e8  jmp     loc_18000A432
0x18006a1c0  push    rbp
0x18006a1c2  sub     rsp, 40h
0x18006a1c6  mov     rbp, rdx
0x18006a1c9  mov     rax, [rcx]
0x18006a1cc  xor     ecx, ecx
0x18006a1ce  cmp     dword ptr [rax], 0C0000006h
0x18006a1d4  setz    cl
0x18006a1d7  mov     eax, ecx
0x18006a1d9  add     rsp, 40h
0x18006a1dd  pop     rbp
0x18006a1de  retn
```
