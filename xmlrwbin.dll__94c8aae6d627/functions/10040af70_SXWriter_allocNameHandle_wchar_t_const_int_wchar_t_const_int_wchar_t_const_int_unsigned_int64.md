# SXWriter::allocNameHandle(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,unsigned __int64 *)

- ea: `0x10040af70`
- end: `0x10040b145`
- name: `?allocNameHandle@SXWriter@@UEAAJPEB_WH0H0HPEA_K@Z`
- size: `469`
- prototype: `int(SXWriter *__hidden this, const wchar_t *, int, const wchar_t *, int, const wchar_t *, int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x100401350`
- `0x100406550`
- `0x100406e50`
- `0x100407330`
- `0x100409da0`
- `0x10040af70`
- `0x100413a50`

## pseudocode

```c
__int64 __fastcall SXWriter::allocNameHandle(
        SXWriter *this,
        wchar_t *a2,
        int a3,
        wchar_t *a4,
        int a5,
        wchar_t *a6,
        int a7,
        unsigned __int64 *a8)
{
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rsi
  unsigned int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // edx
  _DWORD *v18; // rbx
  unsigned int v20; // [rsp+50h] [rbp-68h]
  unsigned int v21[5]; // [rsp+5Ch] [rbp-5Ch] BYREF
  struct CStringPtr *v22[6]; // [rsp+70h] [rbp-48h] BYREF

  v20 = 0;
  if ( !a2 && a3 )
    return (unsigned int)-2147024809;
  if ( !a4 && a5 )
    return (unsigned int)-2147024809;
  if ( !a6 )
    return (unsigned int)-2147024809;
  if ( a5 <= 0 || a7 <= a5 )
    v11 = a7 - a5;
  else
    v11 = a7 - a5 - 1;
  Unitoken::Unitoken((Unitoken *)v22);
  v13 = v12 + 16;
  v14 = *(_DWORD *)(v12 + 36);
  v15 = v14 + 1;
  if ( v14 + 1 < v14 )
  {
    MXRRaiseException(-2147352566);
    goto LABEL_22;
  }
  if ( v15 > *(_DWORD *)(v13 + 16) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)v13, v15, 0x20u);
  }
  SXWriter::getUnitokenFromNames((SXWriter *)((char *)this - 72), a2, a3, a6, v11, a4, a5, v21, (struct Unitoken *)v22);
  *a8 = *((unsigned int *)this + 9);
  v16 = *(_DWORD *)(v13 + 20);
  v17 = v16 + 1;
  if ( v16 + 1 < v16 )
  {
LABEL_22:
    MXRRaiseException(-2147352566);
    __debugbreak();
    JUMPOUT(0x10040B145LL);
  }
  if ( v17 > *(_DWORD *)(v13 + 16) )
  {
    _mm_lfence();
    _varray_base::_ensureCapacity_((_varray_base *)v13, v17, 0x20u);
    v16 = *(_DWORD *)(v13 + 20);
  }
  v18 = (_DWORD *)(*(_QWORD *)(v13 + 24) + 32LL * v16);
  *(_DWORD *)(v13 + 20) = v16 + 1;
  RStringPtr::assign((RStringPtr *)v18, v22[0]);
  RStringPtr::assign((RStringPtr *)(v18 + 2), v22[1]);
  RStringPtr::assign((RStringPtr *)(v18 + 4), v22[2]);
  v18[6] = v21[0];
  WriterHandleEntry::~WriterHandleEntry((WriterHandleEntry *)v22);
  return v20;
}

```

## disassembly

```asm
0x10040af70  mov     [rsp+arg_8], rbx
0x10040af75  mov     [rsp+arg_10], rsi
0x10040af7a  mov     [rsp+arg_18], rdi
0x10040af7f  mov     [rsp+arg_0], rcx
0x10040af84  push    r12
0x10040af86  push    r13
0x10040af88  push    r15
0x10040af8a  sub     rsp, 0A0h
0x10040af91  mov     r15, r9
0x10040af94  mov     r12d, r8d
0x10040af97  mov     r13, rdx
0x10040af9a  mov     rdx, rcx
0x10040af9d  mov     [rsp+0B8h+var_68], 0
0x10040afa5  test    r13, r13
0x10040afa8  jnz     short loc_10040AFBC
0x10040afaa  test    r8d, r8d
0x10040afad  jz      short loc_10040AFBC
0x10040afaf  mov     [rsp+0B8h+var_68], 80070057h
0x10040afb7  jmp     loc_10040B10D
0x10040afbc  mov     edi, [rsp+0B8h+arg_20]
0x10040afc3  test    r15, r15
0x10040afc6  jnz     short loc_10040AFD9
0x10040afc8  test    edi, edi
0x10040afca  jz      short loc_10040AFD9
0x10040afcc  mov     [rsp+0B8h+var_68], 80070057h
0x10040afd4  jmp     loc_10040B10D
0x10040afd9  cmp     [rsp+0B8h+arg_28], 0
0x10040afe2  jnz     short loc_10040AFF1
0x10040afe4  mov     [rsp+0B8h+var_68], 80070057h
0x10040afec  jmp     loc_10040B10D
0x10040aff1  mov     ebx, [rsp+0B8h+arg_30]
0x10040aff8  test    edi, edi
0x10040affa  jle     short loc_10040B006
0x10040affc  cmp     ebx, edi
0x10040affe  jle     short loc_10040B006
0x10040b000  sub     ebx, edi
0x10040b002  dec     ebx
0x10040b004  jmp     short loc_10040B008
0x10040b006  sub     ebx, edi
0x10040b008  lea     rcx, [rsp+0B8h+var_48]; this
0x10040b00d  call    ??0Unitoken@@QEAA@XZ; Unitoken::Unitoken(void)
0x10040b012  lea     rsi, [rdx+10h]
0x10040b016  mov     eax, [rsi+14h]
0x10040b019  lea     edx, [rax+1]; unsigned int
0x10040b01c  cmp     edx, eax
0x10040b01e  jb      loc_10040B12F
0x10040b024  cmp     edx, [rsi+10h]
0x10040b027  jbe     short loc_10040B03A
0x10040b029  lfence
0x10040b02c  mov     r8d, 20h ; ' '; unsigned __int64
0x10040b032  mov     rcx, rsi; this
0x10040b035  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x10040b03a  mov     rcx, [rsp+0B8h+arg_0]
0x10040b042  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x10040b046  lea     rax, [rsp+0B8h+var_48]
0x10040b04b  mov     [rsp+0B8h+var_78], rax; struct Unitoken *
0x10040b050  lea     rax, [rsp+0B8h+var_5C]
0x10040b055  mov     [rsp+0B8h+var_80], rax; unsigned int *
0x10040b05a  mov     [rsp+0B8h+var_88], edi; int
0x10040b05e  mov     [rsp+0B8h+var_90], r15; wchar_t *
0x10040b063  mov     [rsp+0B8h+var_98], ebx; int
0x10040b067  mov     r9, [rsp+0B8h+arg_28]; wchar_t *
0x10040b06f  mov     r8d, r12d; int
0x10040b072  mov     rdx, r13; wchar_t *
0x10040b075  call    ?getUnitokenFromNames@SXWriter@@AEAAXPEB_WH0H0HPEAKPEAVUnitoken@@@Z; SXWriter::getUnitokenFromNames(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ulong *,Unitoken *)
0x10040b07a  mov     rax, [rsp+0B8h+arg_0]
0x10040b082  mov     ecx, [rax+24h]
0x10040b085  mov     rax, [rsp+0B8h+arg_38]
0x10040b08d  mov     [rax], rcx
0x10040b090  mov     eax, [rsi+14h]
0x10040b093  lea     edx, [rax+1]; unsigned int
0x10040b096  cmp     edx, eax
0x10040b098  jb      loc_10040B139
0x10040b09e  cmp     edx, [rsi+10h]
0x10040b0a1  jbe     short loc_10040B0B7
0x10040b0a3  lfence
0x10040b0a6  mov     r8d, 20h ; ' '; unsigned __int64
0x10040b0ac  mov     rcx, rsi; this
0x10040b0af  call    ?_ensureCapacity_@_varray_base@@AEAAXK_K@Z; _varray_base::_ensureCapacity_(ulong,unsigned __int64)
0x10040b0b4  mov     eax, [rsi+14h]
0x10040b0b7  mov     ebx, eax
0x10040b0b9  shl     rbx, 5
0x10040b0bd  add     rbx, [rsi+18h]
0x10040b0c1  inc     eax
0x10040b0c3  mov     [rsi+14h], eax
0x10040b0c6  mov     rdx, [rsp+0B8h+var_48]; struct CStringPtr *
0x10040b0cb  mov     rcx, rbx; this
0x10040b0ce  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040b0d3  lea     rcx, [rbx+8]; this
0x10040b0d7  mov     rdx, [rsp+0B8h+var_40]; struct CStringPtr *
0x10040b0dc  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040b0e1  lea     rcx, [rbx+10h]; this
0x10040b0e5  mov     rdx, [rsp+0B8h+var_38]; struct CStringPtr *
0x10040b0ed  call    ?assign@RStringPtr@@QEAAXPEAVCStringPtr@@@Z; RStringPtr::assign(CStringPtr *)
0x10040b0f2  mov     eax, [rsp+0B8h+var_5C]
0x10040b0f6  mov     [rbx+18h], eax
0x10040b0f9  lea     rcx, [rsp+0B8h+var_48]; this
0x10040b0fe  call    ??1WriterHandleEntry@@QEAA@XZ; WriterHandleEntry::~WriterHandleEntry(void)
0x10040b103  jmp     short loc_10040B10D
0x10040b105  mov     eax, [rsp+0B8h+var_64]
0x10040b109  mov     [rsp+0B8h+var_68], eax
0x10040b10d  mov     eax, [rsp+0B8h+var_68]
0x10040b111  lea     r11, [rsp+0B8h+var_18]
0x10040b119  mov     rbx, [r11+28h]
0x10040b11d  mov     rsi, [r11+30h]
0x10040b121  mov     rdi, [r11+38h]
0x10040b125  mov     rsp, r11
0x10040b128  pop     r15
0x10040b12a  pop     r13
0x10040b12c  pop     r12
0x10040b12e  retn
0x10040b12f  mov     ecx, 8002000Ah; int
0x10040b134  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040b139  mov     ecx, 8002000Ah; int
0x10040b13e  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040b143  nop
0x10040b144  int     3; Trap to Debugger
0x100424ab0  push    rbp
0x100424ab2  sub     rsp, 50h
0x100424ab6  mov     rbp, rdx
0x100424ab9  mov     [rbp+98h], rcx
0x100424ac0  mov     [rbp+68h], rcx
0x100424ac4  mov     rax, [rbp+68h]
0x100424ac8  mov     rcx, [rax]
0x100424acb  mov     [rbp+60h], rcx
0x100424acf  mov     rax, [rbp+60h]
0x100424ad3  mov     eax, [rax]
0x100424ad5  cmp     eax, 0C0000005h
0x100424ada  jz      short loc_100424B0C
0x100424adc  add     eax, 1FFFFFFFh
0x100424ae1  cmp     eax, 1
0x100424ae4  ja      short loc_100424AFC
0x100424ae6  mov     rax, [rbp+60h]
0x100424aea  cmp     dword ptr [rax+18h], 1
0x100424aee  jnz     short loc_100424AFC
0x100424af0  mov     rax, [rbp+60h]
0x100424af4  mov     ecx, [rax+20h]
0x100424af7  mov     [rbp+54h], ecx
0x100424afa  jmp     short loc_100424B03
0x100424afc  mov     dword ptr [rbp+54h], 8000FFFFh
0x100424b03  mov     dword ptr [rbp+58h], 1
0x100424b0a  jmp     short loc_100424B13
0x100424b0c  mov     dword ptr [rbp+58h], 0
0x100424b13  mov     eax, [rbp+58h]
0x100424b16  add     rsp, 50h
0x100424b1a  pop     rbp
0x100424b1b  retn
```
