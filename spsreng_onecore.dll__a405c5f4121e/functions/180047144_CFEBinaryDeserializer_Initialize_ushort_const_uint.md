# CFEBinaryDeserializer::Initialize(ushort const *,uint *)

- ea: `0x180047144`
- end: `0x18004732c`
- name: `?Initialize@CFEBinaryDeserializer@@QEAAJPEBGPEAI@Z`
- size: `488`
- prototype: `__int64 __fastcall(CFEBinaryDeserializer *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180021188`

## callees

- `0x180002470`
- `0x180003ee2`
- `0x180021850`
- `0x180046d54`
- `0x180047144`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800471ff`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047270`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800472cf`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18004730e`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800471ff`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047270`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800472cf`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18004730e`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180047230`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180047230`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18004718d`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180047218`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18004718d`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x180047218`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18004719f`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x18004719f`

## pseudocode

```c
__int64 __fastcall CFEBinaryDeserializer::Initialize(
        CFEBinaryDeserializer *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int v5; // eax
  int v6; // eax
  size_t v7; // rsi
  void *v8; // rax
  __int64 v10; // rax
  unsigned int v11; // edi
  FILE *Stream; // [rsp+58h] [rbp+38h] BYREF

  Stream = 0;
  v5 = CFilePtr::OpenW((CFilePtr *)&Stream, a2, a3);
  if ( !Stream || v5 )
  {
    if ( Stream
      && Stream != o___acrt_iob_func_0(0)
      && Stream != o___acrt_iob_func_0(1u)
      && Stream != o___acrt_iob_func_0(2u) )
    {
      fclose(Stream);
    }
    return 2147811362LL;
  }
  else
  {
    if ( fseek(Stream, 0, 2) )
      goto LABEL_17;
    v6 = _o_ftell(Stream);
    if ( v6 < 0 )
      goto LABEL_17;
    *((_BYTE *)this + 24) = 1;
    v7 = v6;
    v8 = CWinHeap::Alloc((CWinHeap *)&g_heap, v6, 0);
    *(_QWORD *)this = v8;
    if ( !v8 )
    {
      if ( Stream
        && Stream != o___acrt_iob_func_0(0)
        && Stream != o___acrt_iob_func_0(1u)
        && Stream != o___acrt_iob_func_0(2u) )
      {
        fclose(Stream);
      }
      return 2147942414LL;
    }
    if ( fseek(Stream, 0, 0) || fread(*(void **)this, v7, 1u, Stream) != 1 )
    {
LABEL_17:
      if ( Stream
        && Stream != o___acrt_iob_func_0(0)
        && Stream != o___acrt_iob_func_0(1u)
        && Stream != o___acrt_iob_func_0(2u) )
      {
        fclose(Stream);
      }
      return 2147500037LL;
    }
    else
    {
      v10 = *(_QWORD *)this;
      *((_QWORD *)this + 1) = *(_QWORD *)this;
      *((_QWORD *)this + 2) = v7 + v10;
      v11 = CFEBinaryDeserializer::Initialize(this, (unsigned int *)a3);
      if ( Stream
        && Stream != o___acrt_iob_func_0(0)
        && Stream != o___acrt_iob_func_0(1u)
        && Stream != o___acrt_iob_func_0(2u) )
      {
        fclose(Stream);
      }
      return v11;
    }
  }
}

```

## disassembly

```asm
0x180047144  mov     [rsp-18h+arg_0], rbx
0x180047149  mov     [rsp-18h+arg_8], rsi
0x18004714e  push    rbp
0x18004714f  push    rdi
0x180047150  push    r14
0x180047152  mov     rbp, rsp
0x180047155  sub     rsp, 20h
0x180047159  mov     r14, r8
0x18004715c  mov     rdi, rcx
0x18004715f  mov     [rbp+Stream], 0
0x180047167  lea     rcx, [rbp+Stream]; this
0x18004716b  call    ?OpenW@CFilePtr@@QEAAJPEBG0@Z; CFilePtr::OpenW(ushort const *,ushort const *)
0x180047170  mov     rcx, [rbp+Stream]; Stream
0x180047174  test    rcx, rcx
0x180047177  jz      loc_1800472D9
0x18004717d  test    eax, eax
0x18004717f  jnz     loc_1800472D9
0x180047185  lea     ebx, [rax+2]
0x180047188  mov     r8d, ebx; Origin
0x18004718b  xor     edx, edx; Offset
0x18004718d  call    cs:__imp_fseek
0x180047193  test    eax, eax
0x180047195  jnz     loc_18004723C
0x18004719b  mov     rcx, [rbp+Stream]
0x18004719f  call    cs:__imp__o_ftell
0x1800471a5  test    eax, eax
0x1800471a7  js      loc_18004723C
0x1800471ad  mov     byte ptr [rdi+18h], 1
0x1800471b1  movsxd  rsi, eax
0x1800471b4  xor     r8d, r8d; bool
0x1800471b7  mov     rdx, rsi; unsigned __int64
0x1800471ba  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800471c1  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800471c6  mov     [rdi], rax
0x1800471c9  test    rax, rax
0x1800471cc  jnz     short loc_18004720F
0x1800471ce  cmp     [rbp+Stream], rax
0x1800471d2  jz      short loc_180047205
0x1800471d4  xor     ecx, ecx; Ix
0x1800471d6  call    _o___acrt_iob_func_0
0x1800471db  cmp     [rbp+Stream], rax
0x1800471df  jz      short loc_180047205
0x1800471e1  lea     ecx, [rbx-1]; Ix
0x1800471e4  call    _o___acrt_iob_func_0
0x1800471e9  cmp     [rbp+Stream], rax
0x1800471ed  jz      short loc_180047205
0x1800471ef  mov     ecx, ebx; Ix
0x1800471f1  call    _o___acrt_iob_func_0
0x1800471f6  mov     rcx, [rbp+Stream]; Stream
0x1800471fa  cmp     rcx, rax
0x1800471fd  jz      short loc_180047205
0x1800471ff  call    cs:__imp_fclose
0x180047205  mov     eax, 8007000Eh
0x18004720a  jmp     loc_180047319
0x18004720f  xor     r8d, r8d; Origin
0x180047212  xor     edx, edx; Offset
0x180047214  mov     rcx, [rbp+Stream]; Stream
0x180047218  call    cs:__imp_fseek
0x18004721e  test    eax, eax
0x180047220  jnz     short loc_18004723C
0x180047222  mov     r9, [rbp+Stream]; Stream
0x180047226  lea     r8d, [rax+1]; ElementCount
0x18004722a  mov     rdx, rsi; ElementSize
0x18004722d  mov     rcx, [rdi]; Buffer
0x180047230  call    cs:__imp_fread
0x180047236  cmp     rax, 1
0x18004723a  jz      short loc_180047280
0x18004723c  cmp     [rbp+Stream], 0
0x180047241  jz      short loc_180047276
0x180047243  xor     ecx, ecx; Ix
0x180047245  call    _o___acrt_iob_func_0
0x18004724a  cmp     [rbp+Stream], rax
0x18004724e  jz      short loc_180047276
0x180047250  mov     ecx, 1; Ix
0x180047255  call    _o___acrt_iob_func_0
0x18004725a  cmp     [rbp+Stream], rax
0x18004725e  jz      short loc_180047276
0x180047260  mov     ecx, ebx; Ix
0x180047262  call    _o___acrt_iob_func_0
0x180047267  mov     rcx, [rbp+Stream]; Stream
0x18004726b  cmp     rcx, rax
0x18004726e  jz      short loc_180047276
0x180047270  call    cs:__imp_fclose
0x180047276  mov     eax, 80004005h
0x18004727b  jmp     loc_180047319
0x180047280  mov     rax, [rdi]
0x180047283  mov     [rdi+8], rax
0x180047287  add     rax, rsi
0x18004728a  mov     [rdi+10h], rax
0x18004728e  mov     rdx, r14; unsigned int *
0x180047291  mov     rcx, rdi; this
0x180047294  call    ?Initialize@CFEBinaryDeserializer@@AEAAJPEAI@Z; CFEBinaryDeserializer::Initialize(uint *)
0x180047299  mov     edi, eax
0x18004729b  cmp     [rbp+Stream], 0
0x1800472a0  jz      short loc_1800472D5
0x1800472a2  xor     ecx, ecx; Ix
0x1800472a4  call    _o___acrt_iob_func_0
0x1800472a9  cmp     [rbp+Stream], rax
0x1800472ad  jz      short loc_1800472D5
0x1800472af  mov     ecx, 1; Ix
0x1800472b4  call    _o___acrt_iob_func_0
0x1800472b9  cmp     [rbp+Stream], rax
0x1800472bd  jz      short loc_1800472D5
0x1800472bf  mov     ecx, ebx; Ix
0x1800472c1  call    _o___acrt_iob_func_0
0x1800472c6  mov     rcx, [rbp+Stream]; Stream
0x1800472ca  cmp     rcx, rax
0x1800472cd  jz      short loc_1800472D5
0x1800472cf  call    cs:__imp_fclose
0x1800472d5  mov     eax, edi
0x1800472d7  jmp     short loc_180047319
0x1800472d9  test    rcx, rcx
0x1800472dc  jz      short loc_180047314
0x1800472de  xor     ecx, ecx; Ix
0x1800472e0  call    _o___acrt_iob_func_0
0x1800472e5  cmp     [rbp+Stream], rax
0x1800472e9  jz      short loc_180047314
0x1800472eb  mov     ecx, 1; Ix
0x1800472f0  call    _o___acrt_iob_func_0
0x1800472f5  cmp     [rbp+Stream], rax
0x1800472f9  jz      short loc_180047314
0x1800472fb  mov     ecx, 2; Ix
0x180047300  call    _o___acrt_iob_func_0
0x180047305  mov     rcx, [rbp+Stream]; Stream
0x180047309  cmp     rcx, rax
0x18004730c  jz      short loc_180047314
0x18004730e  call    cs:__imp_fclose
0x180047314  mov     eax, 80050022h
0x180047319  mov     rbx, [rsp+20h+arg_0]
0x18004731e  mov     rsi, [rsp+20h+arg_8]
0x180047323  add     rsp, 20h
0x180047327  pop     r14
0x180047329  pop     rdi
0x18004732a  pop     rbp
0x18004732b  retn
```
