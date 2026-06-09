# EcbFileExtentsDumpExtentsIoFormat

- ea: `0x1800b2e48`
- end: `0x1800b303e`
- name: `EcbFileExtentsDumpExtentsIoFormat`
- size: `502`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001c230`

## callees

- `0x1800020b8`
- `0x180020118`
- `0x180020ee8`
- `0x180047bec`
- `0x1800789a8`
- `0x1800b2e48`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!_wfopen` at `0x1800b2ea1`
- `msvcrt!_wfopen` at `0x1800b2ea1`
- `msvcrt!fclose` at `0x1800b3014`
- `msvcrt!fclose` at `0x1800b3014`
- `msvcrt!fprintf` at `0x1800b2ff0`
- `msvcrt!fprintf` at `0x1800b2ff0`

## string_xrefs

- `0x1800b2eb2`: `ERROR: Couldn't open file to write extents %ws\n`

## pseudocode

```c
int __fastcall EcbFileExtentsDumpExtentsIoFormat(__int64 a1, const wchar_t *a2, int a3, __int64 a4)
{
  __int64 v5; // r14
  FILE *v7; // rax
  FILE *v8; // rsi
  unsigned int i; // r12d
  int v10; // r9d
  __int64 *v11; // rbp
  int v12; // ecx
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v18; // [rsp+30h] [rbp-2A8h]
  int v19; // [rsp+50h] [rbp-288h] BYREF
  __int64 *v20; // [rsp+58h] [rbp-280h] BYREF
  __int64 v21; // [rsp+60h] [rbp-278h]
  _BYTE v22[528]; // [rsp+70h] [rbp-268h] BYREF

  v21 = a4;
  v5 = a3;
  v20 = 0;
  v19 = 0;
  if ( a2 )
  {
    v7 = _wfopen(a2, L"w");
    v8 = v7;
    if ( !v7 )
    {
      LODWORD(v7) = EcbUtilsOut(1, "ERROR: Couldn't open file to write extents %ws\n", a2);
      return (int)v7;
    }
  }
  else
  {
    v7 = _acrt_iob_func(1u);
    v8 = v7;
  }
  for ( i = 0; i < *(_DWORD *)(a1 + 4 * v5 + 57372); ++i )
  {
    EcbFileExtentsGetNext(a1, (unsigned int)v5, i, &v20);
    v11 = v20;
    v12 = *((_DWORD *)v20 + 8);
    if ( (v12 & 0x700) == 0x300 )
    {
      v13 = 87;
    }
    else if ( (v12 & 0x700) != 0 )
    {
      switch ( v12 & 0x700 )
      {
        case 256:
          v13 = 77;
          break;
        case 1024:
          v13 = 69;
          break;
        case 512:
          v13 = 80;
          break;
        default:
          v13 = ((v12 & 0x700) != 1280) + 88;
          break;
      }
    }
    else
    {
      v13 = 72;
    }
    if ( (int)v5 < 4 )
      v14 = *(_QWORD *)(v20[1] + 8);
    else
      LODWORD(v14) = *((_DWORD *)v20 + 2);
    LODWORD(v7) = EcbFileNameSpaceGetById(v21, v14, (unsigned int)v22, v10, (__int64)&v19);
    if ( (_DWORD)v7 )
      break;
    v15 = *v11;
    v16 = EcbUtilsTraceBitsToString(*((unsigned __int8 *)v11 + 32));
    LODWORD(v18) = *((_DWORD *)v11 + 5);
    LODWORD(v7) = fprintf(
                    v8,
                    "%wc, %2d, 0x%010I64x, 0x%08I64x, %12d, 1, 1, %s, %ws\n",
                    v13,
                    0,
                    v15 << *((_DWORD *)EcbGlobals + 2193),
                    (unsigned __int64)*((unsigned int *)v11 + 4) << *((_DWORD *)EcbGlobals + 2193),
                    v18,
                    v16,
                    v22);
  }
  if ( v8 )
    LODWORD(v7) = fclose(v8);
  return (int)v7;
}

```

## disassembly

```asm
0x1800b2e48  push    rbx
0x1800b2e4a  push    rbp
0x1800b2e4b  push    rsi
0x1800b2e4c  push    rdi
0x1800b2e4d  push    r12
0x1800b2e4f  push    r13
0x1800b2e51  push    r14
0x1800b2e53  push    r15
0x1800b2e55  sub     rsp, 298h
0x1800b2e5c  mov     rax, cs:__security_cookie
0x1800b2e63  xor     rax, rsp
0x1800b2e66  mov     [rsp+2D8h+var_58], rax
0x1800b2e6e  mov     [rsp+2D8h+var_278], r9
0x1800b2e73  mov     rbx, rdx
0x1800b2e76  movsxd  r14, r8d
0x1800b2e79  mov     r15, rcx
0x1800b2e7c  mov     [rsp+2D8h+var_280], 0
0x1800b2e85  mov     edi, 1
0x1800b2e8a  mov     [rsp+2D8h+var_288], 0
0x1800b2e92  test    rdx, rdx
0x1800b2e95  jz      short loc_1800B2EC5
0x1800b2e97  lea     rdx, aW; "w"
0x1800b2e9e  mov     rcx, rbx; FileName
0x1800b2ea1  call    cs:__imp__wfopen
0x1800b2ea7  mov     rsi, rax
0x1800b2eaa  test    rax, rax
0x1800b2ead  jnz     short loc_1800B2ECF
0x1800b2eaf  mov     r8, rbx
0x1800b2eb2  lea     rdx, aErrorCouldnTOp_0; "ERROR: Couldn't open file to write exte"...
0x1800b2eb9  mov     ecx, edi
0x1800b2ebb  call    EcbUtilsOut
0x1800b2ec0  jmp     loc_1800B301A
0x1800b2ec5  mov     ecx, edi; Ix
0x1800b2ec7  call    __acrt_iob_func
0x1800b2ecc  mov     rsi, rax
0x1800b2ecf  xor     r12d, r12d
0x1800b2ed2  cmp     [r15+r14*4+0E01Ch], r12d
0x1800b2eda  jbe     loc_1800B300C
0x1800b2ee0  mov     ebx, 700h
0x1800b2ee5  lea     r9, [rsp+2D8h+var_280]
0x1800b2eea  mov     r8d, r12d
0x1800b2eed  mov     edx, r14d
0x1800b2ef0  mov     rcx, r15
0x1800b2ef3  call    EcbFileExtentsGetNext
0x1800b2ef8  mov     rbp, [rsp+2D8h+var_280]
0x1800b2efd  mov     ecx, [rbp+20h]
0x1800b2f00  mov     eax, ecx
0x1800b2f02  and     eax, ebx
0x1800b2f04  cmp     eax, 300h
0x1800b2f09  jnz     short loc_1800B2F12
0x1800b2f0b  mov     edi, 57h ; 'W'
0x1800b2f10  jmp     short loc_1800B2F64
0x1800b2f12  test    ebx, ecx
0x1800b2f14  jnz     short loc_1800B2F1D
0x1800b2f16  mov     edi, 48h ; 'H'
0x1800b2f1b  jmp     short loc_1800B2F64
0x1800b2f1d  mov     eax, ecx
0x1800b2f1f  and     eax, ebx
0x1800b2f21  cmp     eax, 100h
0x1800b2f26  jnz     short loc_1800B2F2F
0x1800b2f28  mov     edi, 4Dh ; 'M'
0x1800b2f2d  jmp     short loc_1800B2F64
0x1800b2f2f  mov     eax, ecx
0x1800b2f31  and     eax, ebx
0x1800b2f33  cmp     eax, 400h
0x1800b2f38  jnz     short loc_1800B2F41
0x1800b2f3a  mov     edi, 45h ; 'E'
0x1800b2f3f  jmp     short loc_1800B2F64
0x1800b2f41  mov     eax, ecx
0x1800b2f43  and     eax, ebx
0x1800b2f45  cmp     eax, 200h
0x1800b2f4a  jnz     short loc_1800B2F53
0x1800b2f4c  mov     edi, 50h ; 'P'
0x1800b2f51  jmp     short loc_1800B2F64
0x1800b2f53  xor     edi, edi
0x1800b2f55  and     ecx, ebx
0x1800b2f57  cmp     ecx, 500h
0x1800b2f5d  setnz   dil
0x1800b2f61  add     edi, 58h ; 'X'
0x1800b2f64  cmp     r14d, 4
0x1800b2f68  jl      short loc_1800B2F6F
0x1800b2f6a  mov     edx, [rbp+8]
0x1800b2f6d  jmp     short loc_1800B2F77
0x1800b2f6f  mov     rax, [rbp+8]
0x1800b2f73  mov     rdx, [rax+8]
0x1800b2f77  mov     rcx, [rsp+2D8h+var_278]
0x1800b2f7c  lea     rax, [rsp+2D8h+var_288]
0x1800b2f81  lea     r8, [rsp+2D8h+var_268]
0x1800b2f86  mov     [rsp+2D8h+var_2B8], rax
0x1800b2f8b  call    EcbFileNameSpaceGetById
0x1800b2f90  test    eax, eax
0x1800b2f92  jnz     short loc_1800B300C
0x1800b2f94  mov     ebx, [rbp+4]
0x1800b2f97  mov     eax, [rbp+0]
0x1800b2f9a  movzx   ecx, byte ptr [rbp+20h]
0x1800b2f9e  shl     rbx, 20h
0x1800b2fa2  or      rbx, rax
0x1800b2fa5  call    EcbUtilsTraceBitsToString
0x1800b2faa  mov     rcx, cs:EcbGlobals
0x1800b2fb1  xor     r9d, r9d
0x1800b2fb4  mov     edx, [rbp+10h]
0x1800b2fb7  mov     r8d, edi
0x1800b2fba  mov     ecx, [rcx+2244h]
0x1800b2fc0  shl     rdx, cl
0x1800b2fc3  shl     rbx, cl
0x1800b2fc6  lea     rcx, [rsp+2D8h+var_268]
0x1800b2fcb  mov     [rsp+2D8h+var_298], rcx
0x1800b2fd0  mov     rcx, rsi; Stream
0x1800b2fd3  mov     [rsp+2D8h+var_2A0], rax
0x1800b2fd8  mov     eax, [rbp+14h]
0x1800b2fdb  mov     dword ptr [rsp+2D8h+var_2A8], eax
0x1800b2fdf  mov     [rsp+2D8h+var_2B0], rdx
0x1800b2fe4  lea     rdx, aWc2d0x010i64x0; "%wc, %2d, 0x%010I64x, 0x%08I64x, %12d, "...
0x1800b2feb  mov     [rsp+2D8h+var_2B8], rbx
0x1800b2ff0  call    cs:__imp_fprintf
0x1800b2ff6  inc     r12d
0x1800b2ff9  mov     ebx, 700h
0x1800b2ffe  cmp     r12d, [r15+r14*4+0E01Ch]
0x1800b3006  jb      loc_1800B2EE5
0x1800b300c  test    rsi, rsi
0x1800b300f  jz      short loc_1800B301A
0x1800b3011  mov     rcx, rsi; Stream
0x1800b3014  call    cs:__imp_fclose
0x1800b301a  mov     rcx, [rsp+2D8h+var_58]
0x1800b3022  xor     rcx, rsp; StackCookie
0x1800b3025  call    __security_check_cookie
0x1800b302a  add     rsp, 298h
0x1800b3031  pop     r15
0x1800b3033  pop     r14
0x1800b3035  pop     r13
0x1800b3037  pop     r12
0x1800b3039  pop     rdi
0x1800b303a  pop     rsi
0x1800b303b  pop     rbp
0x1800b303c  pop     rbx
0x1800b303d  retn
```
