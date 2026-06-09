# _hypothesis_builder::AppendAndDetach(ulong,_hypothesis_builder *,ulong *,tagHYPOTHESIS * *)

- ea: `0x180012794`
- end: `0x180012939`
- name: `?AppendAndDetach@_hypothesis_builder@@QEAAJKPEAV1@PEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `421`
- prototype: `__int64 __usercall@<rax>(_hypothesis_builder *__hidden this@<rcx>, unsigned int@<edx>, struct _hypothesis_builder *@<r8>, unsigned int *@<r9>, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b30`

## callees

- `0x180012794`
- `0x180012a5c`
- `0x180012b10`
- `0x180012ca0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800128e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012857`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::AppendAndDetach(
        _hypothesis_builder *this,
        unsigned int a2,
        struct _hypothesis_builder *a3,
        unsigned int *a4,
        struct tagHYPOTHESIS **a5)
{
  struct tagHYPOTHESIS **v5; // r12
  unsigned int v6; // r14d
  __int64 result; // rax
  SIZE_T v12; // rsi
  struct tagHYPOTHESIS *v13; // rax
  struct tagHYPOTHESIS *v14; // rdi
  int v15; // ebx
  unsigned int v16; // esi
  struct tagHYPOTHESIS *v17; // rbx
  __int64 v18; // rdi
  _BYTE *v19; // rax
  unsigned int v20[22]; // [rsp+20h] [rbp-58h] BYREF

  v5 = a5;
  v6 = 0;
  if ( !a5 || !a4 )
    return 2147942487LL;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a2 > 0x7FFFFFE )
        return 2147942934LL;
      v12 = 32LL * (a2 + 1);
      v13 = (struct tagHYPOTHESIS *)CoTaskMemAlloc(v12);
      v14 = v13;
      if ( !v13 )
        return 2147942414LL;
      for ( ; v12; --v12 )
      {
        LOBYTE(v13->pwszClassName) = 0;
        v13 = (struct tagHYPOTHESIS *)((char *)v13 + 1);
      }
      v20[0] = 0;
      LODWORD(a5) = 0;
      v15 = _hypothesis_builder::DetachInPlace(this, v14, (unsigned int *)&a5, v20);
      if ( v15 >= 0 )
      {
        v16 = (unsigned int)a5;
        v17 = (struct tagHYPOTHESIS *)((char *)v14 + v20[0]);
        if ( a2 )
        {
          do
          {
            if ( (int)_hypothesis_builder::DetachInPlace(
                        (struct _hypothesis_builder *)((char *)a3 + 40 * v6),
                        v17,
                        (unsigned int *)&a5,
                        v20) < 0 )
              break;
            ++v6;
            v16 += (unsigned int)a5;
            v17 = (struct tagHYPOTHESIS *)((char *)v17 + v20[0]);
          }
          while ( v6 < a2 );
        }
        *v5 = v14;
        result = 0;
        *a4 = v16;
      }
      else
      {
        CoTaskMemFree(v14);
        return (unsigned int)v15;
      }
      return result;
    }
    return 2147942487LL;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v18 = 32;
    v19 = CoTaskMemAlloc(0x20u);
    *((_QWORD *)this + 4) = v19;
    if ( !v19 )
      return 2147942414LL;
    do
    {
      *v19++ = 0;
      --v18;
    }
    while ( v18 );
  }
  _hypothesis_builder::DoDetach(this, v5);
  result = 0;
  *a4 = 1;
  return result;
}

```

## disassembly

```asm
0x180012794  push    rbx
0x180012796  push    rbp
0x180012797  push    rsi
0x180012798  push    rdi
0x180012799  push    r12
0x18001279b  push    r13
0x18001279d  push    r14
0x18001279f  push    r15
0x1800127a1  sub     rsp, 38h
0x1800127a5  mov     r12, [rsp+78h+arg_20]
0x1800127ad  xor     r14d, r14d
0x1800127b0  mov     r15, r9
0x1800127b3  mov     r13, r8
0x1800127b6  mov     ebp, edx
0x1800127b8  mov     rbx, rcx
0x1800127bb  test    r12, r12
0x1800127be  jz      loc_180012922
0x1800127c4  test    r9, r9
0x1800127c7  jz      loc_180012922
0x1800127cd  test    edx, edx
0x1800127cf  jz      loc_1800128C8
0x1800127d5  test    r8, r8
0x1800127d8  jz      loc_180012922
0x1800127de  cmp     edx, 7FFFFFEh
0x1800127e4  jbe     short loc_1800127F0
0x1800127e6  mov     eax, 80070216h
0x1800127eb  jmp     loc_180012927
0x1800127f0  lea     esi, [rdx+1]
0x1800127f3  shl     rsi, 5
0x1800127f7  mov     rcx, rsi; cb
0x1800127fa  call    cs:__imp_CoTaskMemAlloc
0x180012801  nop     dword ptr [rax+rax+00h]
0x180012806  mov     rdi, rax
0x180012809  test    rax, rax
0x18001280c  jnz     short loc_180012818
0x18001280e  mov     eax, 8007000Eh
0x180012813  jmp     loc_180012927
0x180012818  test    rsi, rsi
0x18001281b  jz      short loc_180012829
0x18001281d  mov     [rax], r14b
0x180012820  inc     rax
0x180012823  sub     rsi, 1
0x180012827  jnz     short loc_18001281D
0x180012829  lea     r9, [rsp+78h+var_58]; unsigned int *
0x18001282e  mov     [rsp+78h+var_58], r14d
0x180012833  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x18001283b  mov     dword ptr [rsp+78h+arg_20], r14d
0x180012843  mov     rdx, rdi; struct tagHYPOTHESIS *
0x180012846  mov     rcx, rbx; this
0x180012849  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x18001284e  mov     ebx, eax
0x180012850  test    eax, eax
0x180012852  jns     short loc_18001286A
0x180012854  mov     rcx, rdi; pv
0x180012857  call    cs:__imp_CoTaskMemFree
0x18001285e  nop     dword ptr [rax+rax+00h]
0x180012863  mov     eax, ebx
0x180012865  jmp     loc_180012927
0x18001286a  mov     ebx, [rsp+78h+var_58]
0x18001286e  mov     esi, dword ptr [rsp+78h+arg_20]
0x180012875  add     rbx, rdi
0x180012878  test    ebp, ebp
0x18001287a  jz      short loc_1800128BD
0x18001287c  mov     eax, r14d
0x18001287f  lea     r9, [rsp+78h+var_58]; unsigned int *
0x180012884  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x18001288c  mov     rdx, rbx; struct tagHYPOTHESIS *
0x18001288f  lea     rcx, [rax+rax*4]
0x180012893  lea     rcx, ds:0[rcx*8]
0x18001289b  add     rcx, r13; this
0x18001289e  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x1800128a3  test    eax, eax
0x1800128a5  js      short loc_1800128BD
0x1800128a7  mov     eax, [rsp+78h+var_58]
0x1800128ab  inc     r14d
0x1800128ae  add     esi, dword ptr [rsp+78h+arg_20]
0x1800128b5  add     rbx, rax
0x1800128b8  cmp     r14d, ebp
0x1800128bb  jb      short loc_18001287C
0x1800128bd  mov     [r12], rdi
0x1800128c1  xor     eax, eax
0x1800128c3  mov     [r15], esi
0x1800128c6  jmp     short loc_180012927
0x1800128c8  cmp     [rcx+20h], r14
0x1800128cc  jnz     short loc_18001290B
0x1800128ce  cmp     [rcx+10h], r14d
0x1800128d2  jnz     short loc_1800128DA
0x1800128d4  cmp     [rcx+18h], r14
0x1800128d8  jz      short loc_1800128DF
0x1800128da  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800128df  mov     edi, 20h ; ' '
0x1800128e4  mov     ecx, edi; cb
0x1800128e6  call    cs:__imp_CoTaskMemAlloc
0x1800128ed  nop     dword ptr [rax+rax+00h]
0x1800128f2  mov     [rbx+20h], rax
0x1800128f6  test    rax, rax
0x1800128f9  jz      loc_18001280E
0x1800128ff  mov     [rax], r14b
0x180012902  inc     rax
0x180012905  sub     rdi, 1
0x180012909  jnz     short loc_1800128FF
0x18001290b  mov     rdx, r12; struct tagHYPOTHESIS **
0x18001290e  mov     rcx, rbx; this
0x180012911  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x180012916  mov     eax, r14d
0x180012919  mov     dword ptr [r15], 1
0x180012920  jmp     short loc_180012927
0x180012922  mov     eax, 80070057h
0x180012927  add     rsp, 38h
0x18001292b  pop     r15
0x18001292d  pop     r14
0x18001292f  pop     r13
0x180012931  pop     r12
0x180012933  pop     rdi
0x180012934  pop     rsi
0x180012935  pop     rbp
0x180012936  pop     rbx
0x180012937  retn
```
