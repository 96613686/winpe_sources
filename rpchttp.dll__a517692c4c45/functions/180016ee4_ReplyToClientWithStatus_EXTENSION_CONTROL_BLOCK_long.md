# ReplyToClientWithStatus(_EXTENSION_CONTROL_BLOCK *,long)

- ea: `0x180016ee4`
- end: `0x180017304`
- name: `?ReplyToClientWithStatus@@YAJPEAU_EXTENSION_CONTROL_BLOCK@@J@Z`
- size: `1056`
- prototype: `int(struct _EXTENSION_CONTROL_BLOCK *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003b00`
- `0x18001b920`

## callees

- `0x180002238`
- `0x180016ee4`
- `0x18002461d`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!_itoa_s` at `0x180016f66`
- `ntdll!_itoa_s` at `0x180016f66`
- `KERNEL32!GetLastError` at `0x18001727d`
- `KERNEL32!GetLastError` at `0x18001727d`
- `RPCRT4!I_RpcFree` at `0x180017077`
- `RPCRT4!I_RpcFree` at `0x180017150`
- `RPCRT4!I_RpcFree` at `0x180017294`
- `RPCRT4!I_RpcFree` at `0x1800172a6`
- `RPCRT4!I_RpcFree` at `0x1800172b4`
- `RPCRT4!I_RpcFree` at `0x1800172c2`
- `RPCRT4!I_RpcFree` at `0x1800172d5`
- `RPCRT4!I_RpcFree` at `0x180017077`
- `RPCRT4!I_RpcFree` at `0x180017150`
- `RPCRT4!I_RpcFree` at `0x180017294`
- `RPCRT4!I_RpcFree` at `0x1800172a6`
- `RPCRT4!I_RpcFree` at `0x1800172b4`
- `RPCRT4!I_RpcFree` at `0x1800172c2`
- `RPCRT4!I_RpcFree` at `0x1800172d5`
- `RPCRT4!I_RpcAllocate` at `0x180016fe8`
- `RPCRT4!I_RpcAllocate` at `0x180017044`
- `RPCRT4!I_RpcAllocate` at `0x1800170ba`
- `RPCRT4!I_RpcAllocate` at `0x180017119`
- `RPCRT4!I_RpcAllocate` at `0x18001715c`
- `RPCRT4!I_RpcAllocate` at `0x180016fe8`
- `RPCRT4!I_RpcAllocate` at `0x180017044`
- `RPCRT4!I_RpcAllocate` at `0x1800170ba`
- `RPCRT4!I_RpcAllocate` at `0x180017119`
- `RPCRT4!I_RpcAllocate` at `0x18001715c`
- `RPCRT4!I_RpcLogEvent` at `0x180016f52`
- `RPCRT4!I_RpcLogEvent` at `0x180016f52`

## pseudocode

```c
__int64 __fastcall ReplyToClientWithStatus(struct _EXTENSION_CONTROL_BLOCK *a1, __int64 a2)
{
  int v2; // ebx
  struct _EXTENSION_CONTROL_BLOCK *v3; // r8
  unsigned __int8 *v4; // r12
  char *v5; // r13
  int v6; // edi
  unsigned __int8 *v7; // r15
  __int64 v8; // rbx
  unsigned int v9; // r14d
  __int64 v10; // rcx
  __int64 v11; // rax
  void *v12; // rax
  unsigned int v13; // r9d
  __int64 v14; // rax
  char *v15; // rax
  unsigned int v16; // r9d
  unsigned int v17; // eax
  unsigned int v18; // ecx
  char *v19; // rax
  char *v20; // rsi
  char *v21; // rdi
  int v22; // ecx
  char *v23; // rdi
  __int64 v24; // rbx
  __int64 v25; // rbx
  void *v26; // rdx
  size_t v27; // r8
  int v28; // r14d
  unsigned int v29; // ebx
  int v31; // [rsp+20h] [rbp-49h]
  unsigned int Size[2]; // [rsp+40h] [rbp-29h] BYREF
  int v33; // [rsp+48h] [rbp-21h]
  int v34; // [rsp+4Ch] [rbp-1Dh]
  size_t v35; // [rsp+50h] [rbp-19h]
  int v36; // [rsp+58h] [rbp-11h] BYREF
  void *Src; // [rsp+60h] [rbp-9h]
  struct _EXTENSION_CONTROL_BLOCK *v38; // [rsp+68h] [rbp-1h]
  char Buffer[16]; // [rsp+70h] [rbp+7h] BYREF

  v38 = a1;
  v2 = a2;
  v3 = a1;
  v31 = a2;
  LOBYTE(a2) = 75;
  v36 = 0;
  LOBYTE(a1) = 50;
  *(_QWORD *)Size = 0;
  v34 = 0;
  v4 = 0;
  v35 = 0;
  v5 = 0;
  v6 = 0;
  v33 = 0;
  v7 = 0;
  Src = 0;
  I_RpcLogEvent(a1, a2, v3, 0, v31, 1, 0);
  _itoa_s(v2, Buffer, 9u, 16);
  v8 = -1;
  do
    ++v8;
  while ( Buffer[v8] );
  v9 = v8 + 29;
  if ( *((_DWORD *)pRuntimeImportTable + 145) )
  {
    v10 = (*((__int64 (**)(void))pRuntimeImportTable + 63))();
    if ( v10 )
    {
      (*((void (__fastcall **)(__int64))pRuntimeImportTable + 64))(v10);
      (*((void (__fastcall **)(__int64, unsigned int *))pRuntimeImportTable + 65))(18429, Size);
      if ( *(_QWORD *)Size )
      {
        v7 = (unsigned __int8 *)I_RpcAllocate(Size[0]);
        if ( v7 )
        {
          v11 = (*((__int64 (**)(void))pRuntimeImportTable + 63))();
          if ( !(*((unsigned int (__fastcall **)(__int64, unsigned __int8 *, _QWORD))pRuntimeImportTable + 66))(
                  v11,
                  v7,
                  *(_QWORD *)Size) )
          {
            v12 = I_RpcAllocate((4 * Size[0] + 8) / 3 + 1);
            Src = v12;
            if ( v12 )
            {
              HIDWORD(v35) = RpcpBase64Encode(v7, Size[0], (char *)v12, v13);
              v6 = 1;
              v33 = 1;
              v9 += HIDWORD(v35) + 25;
              I_RpcFree(v7);
              v7 = 0;
            }
            else
            {
              v6 = 0;
            }
          }
        }
      }
      (*((void (__fastcall **)(_QWORD, unsigned int *))pRuntimeImportTable + 65))(
        ((unsigned int)(3 * (989 - v8)) >> 2) - 2,
        Size);
      if ( *(_QWORD *)Size )
      {
        v4 = (unsigned __int8 *)I_RpcAllocate(Size[0]);
        if ( v4 )
        {
          v14 = (*((__int64 (**)(void))pRuntimeImportTable + 63))();
          if ( !(*((unsigned int (__fastcall **)(__int64, unsigned __int8 *, _QWORD))pRuntimeImportTable + 66))(
                  v14,
                  v4,
                  *(_QWORD *)Size) )
          {
            v15 = (char *)I_RpcAllocate((4 * Size[0] + 8) / 3 + 1);
            v5 = v15;
            if ( v15 )
            {
              v17 = RpcpBase64Encode(v4, Size[0], v15, v16);
              v18 = v9 + 10;
              LODWORD(v35) = v17;
              v34 = 1;
              if ( v6 )
                v18 = v9;
              v9 = v17 + v18;
              I_RpcFree(v4);
              v4 = 0;
            }
          }
        }
      }
    }
  }
  v19 = (char *)I_RpcAllocate(v9);
  v20 = v19;
  if ( v19 )
  {
    v21 = v19 + 24;
    qmemcpy(v19, "HTTP/1.0 503 RPC Error: ", 24);
    memcpy_0(v19 + 24, Buffer, (unsigned int)v8);
    v22 = v34;
    v23 = &v21[(unsigned int)v8];
    if ( !v34 && !v33 )
      goto LABEL_25;
    qmemcpy(v23, ", EEInfo: ", 10);
    v23 += 10;
    if ( v22 )
    {
      v24 = (unsigned int)v35;
      memcpy_0(v23, v5, (unsigned int)v35);
      v23 += v24;
    }
    if ( v33 )
    {
      v25 = HIDWORD(v35);
      v26 = Src;
      v27 = HIDWORD(v35);
      qmemcpy(v23, "\r\n\r\nRPC EEInfo:", 15);
      memcpy_0(v23 + 15, v26, v27);
      strcpy(&v23[v25 + 15], "\r\n\r\n");
    }
    else
    {
LABEL_25:
      strcpy(v23, "\r\n\r\n");
    }
    v28 = v9 - 1;
  }
  else
  {
    v20 = "HTTP/1.0 500 Out of memory\r\n\r\n";
    v28 = 30;
  }
  v36 = v28;
  if ( ((unsigned int (__fastcall *)(HCONN, char *, int *, __int64))v38->WriteClient)(v38->ConnID, v20, &v36, 4097) )
  {
    v29 = 0;
  }
  else
  {
    GetLastError();
    v29 = 14;
  }
  if ( v7 )
    I_RpcFree(v7);
  if ( Src )
    I_RpcFree(Src);
  if ( v4 )
    I_RpcFree(v4);
  if ( v5 )
    I_RpcFree(v5);
  if ( v20 && v20 != "HTTP/1.0 500 Out of memory\r\n\r\n" )
    I_RpcFree(v20);
  return v29;
}

```

## disassembly

```asm
0x180016ee4  mov     [rsp-8+arg_10], rbx
0x180016ee9  push    rbp
0x180016eea  push    rsi
0x180016eeb  push    rdi
0x180016eec  push    r12
0x180016eee  push    r13
0x180016ef0  push    r14
0x180016ef2  push    r15
0x180016ef4  lea     rbp, [rsp-27h]
0x180016ef9  sub     rsp, 90h
0x180016f00  mov     rax, cs:__security_cookie
0x180016f07  xor     rax, rsp
0x180016f0a  mov     [rbp+57h+var_40], rax
0x180016f0e  xor     esi, esi
0x180016f10  mov     [rbp+57h+var_58], rcx
0x180016f14  mov     [rsp+0C0h+var_90], esi
0x180016f18  mov     ebx, edx
0x180016f1a  mov     r8, rcx
0x180016f1d  mov     [rsp+0C0h+var_98], 1
0x180016f25  mov     [rsp+0C0h+var_A0], edx
0x180016f29  xor     r9d, r9d
0x180016f2c  mov     dl, 4Bh ; 'K'
0x180016f2e  mov     [rbp+57h+var_68], esi
0x180016f31  mov     cl, 32h ; '2'
0x180016f33  mov     qword ptr [rbp+57h+Size], rsi
0x180016f37  mov     [rbp+57h+var_74], esi
0x180016f3a  mov     r12d, esi
0x180016f3d  mov     dword ptr [rbp+57h+var_70], esi
0x180016f40  mov     r13d, esi
0x180016f43  mov     edi, esi
0x180016f45  mov     [rbp+57h+var_78], esi
0x180016f48  mov     r15d, esi
0x180016f4b  mov     dword ptr [rbp+57h+var_70+4], esi
0x180016f4e  mov     [rbp+57h+Src], rsi
0x180016f52  call    cs:__imp_I_RpcLogEvent
0x180016f58  lea     r9d, [rsi+10h]; Radix
0x180016f5c  mov     ecx, ebx; Value
0x180016f5e  lea     r8d, [rsi+9]; BufferCount
0x180016f62  lea     rdx, [rbp+57h+Buffer]; Buffer
0x180016f66  call    cs:__imp__itoa_s
0x180016f6c  lea     rax, [rbp+57h+Buffer]
0x180016f70  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180016f74  inc     rbx
0x180016f77  cmp     [rax+rbx], sil
0x180016f7b  jnz     short loc_180016F74
0x180016f7d  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180016f84  lea     r14d, [rbx+1Dh]
0x180016f88  cmp     [rax+244h], esi
0x180016f8e  jz      loc_180017159
0x180016f94  mov     rax, [rax+1F8h]
0x180016f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa0  mov     rcx, rax
0x180016fa3  test    rax, rax
0x180016fa6  jz      loc_180017159
0x180016fac  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180016fb3  mov     rax, [rax+200h]
0x180016fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fbf  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180016fc6  lea     rdx, [rbp+57h+Size]
0x180016fca  mov     ecx, 47FDh
0x180016fcf  mov     rax, [rax+208h]
0x180016fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fdb  mov     rcx, qword ptr [rbp+57h+Size]; Size
0x180016fdf  test    rcx, rcx
0x180016fe2  jz      loc_180017086
0x180016fe8  call    cs:__imp_I_RpcAllocate
0x180016fee  mov     r15, rax
0x180016ff1  test    rax, rax
0x180016ff4  jz      loc_180017086
0x180016ffa  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x180017001  mov     rax, [rax+1F8h]
0x180017008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001700d  mov     r8, qword ptr [rbp+57h+Size]
0x180017011  mov     rcx, rax
0x180017014  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001701b  mov     rdx, r15
0x18001701e  mov     rax, [rax+210h]
0x180017025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001702a  test    eax, eax
0x18001702c  jnz     short loc_180017086
0x18001702e  mov     eax, [rbp+57h+Size]
0x180017031  lea     ecx, ds:8[rax*4]
0x180017038  mov     eax, 0AAAAAAABh
0x18001703d  mul     ecx
0x18001703f  shr     edx, 1
0x180017041  lea     ecx, [rdx+1]; Size
0x180017044  call    cs:__imp_I_RpcAllocate
0x18001704a  mov     [rbp+57h+Src], rax
0x18001704e  test    rax, rax
0x180017051  jz      short loc_180017084
0x180017053  mov     edx, [rbp+57h+Size]; unsigned int
0x180017056  mov     r8, rax; char *
0x180017059  mov     rcx, r15; unsigned __int8 *
0x18001705c  call    ?RpcpBase64Encode@@YAKPEAEKPEADK@Z; RpcpBase64Encode(uchar *,ulong,char *,ulong)
0x180017061  mov     esi, eax
0x180017063  mov     dword ptr [rbp+57h+var_70+4], eax
0x180017066  add     esi, 19h
0x180017069  mov     edi, 1
0x18001706e  mov     rcx, r15; Object
0x180017071  mov     [rbp+57h+var_78], edi
0x180017074  add     r14d, esi
0x180017077  call    cs:__imp_I_RpcFree
0x18001707d  xor     esi, esi
0x18001707f  mov     r15d, esi
0x180017082  jmp     short loc_180017086
0x180017084  mov     edi, esi
0x180017086  mov     eax, 3DDh
0x18001708b  lea     rdx, [rbp+57h+Size]
0x18001708f  sub     eax, ebx
0x180017091  lea     ecx, [rax+rax*2]
0x180017094  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001709b  shr     ecx, 2
0x18001709e  sub     ecx, 2
0x1800170a1  mov     rax, [rax+208h]
0x1800170a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ad  mov     rcx, qword ptr [rbp+57h+Size]; Size
0x1800170b1  test    rcx, rcx
0x1800170b4  jz      loc_180017159
0x1800170ba  call    cs:__imp_I_RpcAllocate
0x1800170c0  mov     r12, rax
0x1800170c3  test    rax, rax
0x1800170c6  jz      loc_180017159
0x1800170cc  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800170d3  mov     rax, [rcx+1F8h]
0x1800170da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170df  mov     rcx, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x1800170e6  mov     r9, rax
0x1800170e9  mov     r8, qword ptr [rbp+57h+Size]
0x1800170ed  mov     rdx, r12
0x1800170f0  mov     rax, [rcx+210h]
0x1800170f7  mov     rcx, r9
0x1800170fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ff  test    eax, eax
0x180017101  jnz     short loc_180017159
0x180017103  mov     ecx, [rbp+57h+Size]
0x180017106  mov     eax, 0AAAAAAABh
0x18001710b  lea     ecx, ds:8[rcx*4]
0x180017112  mul     ecx
0x180017114  shr     edx, 1
0x180017116  lea     ecx, [rdx+1]; Size
0x180017119  call    cs:__imp_I_RpcAllocate
0x18001711f  mov     r13, rax
0x180017122  test    rax, rax
0x180017125  jz      short loc_180017159
0x180017127  mov     edx, [rbp+57h+Size]; unsigned int
0x18001712a  mov     r8, rax; char *
0x18001712d  mov     rcx, r12; unsigned __int8 *
0x180017130  call    ?RpcpBase64Encode@@YAKPEAEKPEADK@Z; RpcpBase64Encode(uchar *,ulong,char *,ulong)
0x180017135  lea     ecx, [r14+0Ah]
0x180017139  mov     dword ptr [rbp+57h+var_70], eax
0x18001713c  test    edi, edi
0x18001713e  mov     [rbp+57h+var_74], 1
0x180017145  cmovnz  ecx, r14d
0x180017149  lea     r14d, [rax+rcx]
0x18001714d  mov     rcx, r12; Object
0x180017150  call    cs:__imp_I_RpcFree
0x180017156  mov     r12, rsi
0x180017159  mov     ecx, r14d; Size
0x18001715c  call    cs:__imp_I_RpcAllocate
0x180017162  lea     rdi, aHttp10500OutOf; "HTTP/1.0 500 Out of memory\r\n\r\n"
0x180017169  mov     rsi, rax
0x18001716c  test    rax, rax
0x18001716f  jz      loc_18001724B
0x180017175  movups  xmm0, cs:xmmword_180028488
0x18001717c  lea     rdi, [rax+18h]
0x180017180  mov     ebx, ebx
0x180017182  mov     r8d, ebx; Size
0x180017185  lea     rdx, [rbp+57h+Buffer]; Src
0x180017189  movups  xmmword ptr [rax], xmm0
0x18001718c  mov     rcx, rdi; void *
0x18001718f  movsd   xmm1, cs:qword_180028498
0x180017197  movsd   qword ptr [rax+10h], xmm1
0x18001719c  call    memcpy_0
0x1800171a1  mov     ecx, [rbp+57h+var_74]
0x1800171a4  add     rdi, rbx
0x1800171a7  test    ecx, ecx
0x1800171a9  jnz     short loc_1800171B0
0x1800171ab  cmp     [rbp+57h+var_78], ecx
0x1800171ae  jz      short loc_18001722E
0x1800171b0  movsd   xmm0, cs:qword_180028478
0x1800171b8  movsd   qword ptr [rdi], xmm0
0x1800171bc  movzx   eax, cs:word_180028480
0x1800171c3  mov     [rdi+8], ax
0x1800171c7  add     rdi, 0Ah
0x1800171cb  test    ecx, ecx
0x1800171cd  jz      short loc_1800171E3
0x1800171cf  mov     ebx, dword ptr [rbp+57h+var_70]
0x1800171d2  mov     rdx, r13; Src
0x1800171d5  mov     r8d, ebx; Size
0x1800171d8  mov     rcx, rdi; void *
0x1800171db  call    memcpy_0
0x1800171e0  add     rdi, rbx
0x1800171e3  cmp     [rbp+57h+var_78], 0
0x1800171e7  jz      short loc_18001722E
0x1800171e9  mov     ebx, dword ptr [rbp+57h+var_70+4]
0x1800171ec  lea     rcx, [rdi+0Fh]; void *
0x1800171f0  mov     rdx, [rbp+57h+Src]; Src
0x1800171f4  mov     r8d, ebx; Size
0x1800171f7  mov     dword ptr [rdi], 0A0D0A0Dh
0x1800171fd  movsd   xmm0, qword ptr cs:aRpcEeinfo; "RPC EEInfo:"
0x180017205  movsd   qword ptr [rdi+4], xmm0
0x18001720a  mov     eax, dword ptr cs:aRpcEeinfo+7; "nfo:"
0x180017210  mov     [rdi+0Bh], eax
0x180017213  call    memcpy_0
0x180017218  mov     eax, cs:dword_180028458
0x18001721e  mov     [rbx+rdi+0Fh], eax
0x180017222  mov     al, cs:byte_18002845C
0x180017228  mov     [rbx+rdi+13h], al
0x18001722c  jmp     short loc_18001723F
0x18001722e  mov     eax, cs:dword_18002846C
0x180017234  mov     [rdi], eax
0x180017236  mov     al, cs:byte_180028470
0x18001723c  mov     [rdi+4], al
0x18001723f  dec     r14d
0x180017242  lea     rdi, aHttp10500OutOf; "HTTP/1.0 500 Out of memory\r\n\r\n"
0x180017249  jmp     short loc_180017254
0x18001724b  mov     rsi, rdi
0x18001724e  mov     r14d, 1Eh
0x180017254  mov     rax, [rbp+57h+var_58]
0x180017258  lea     r8, [rbp+57h+var_68]
0x18001725c  mov     r9d, 1001h
0x180017262  mov     [rbp+57h+var_68], r14d
0x180017266  mov     rdx, rsi
0x180017269  mov     rcx, [rax+8]
0x18001726d  mov     rax, [rax+0A8h]
0x180017274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017279  test    eax, eax
0x18001727b  jnz     short loc_18001728A
0x18001727d  call    cs:__imp_GetLastError
0x180017283  mov     ebx, 0Eh
0x180017288  jmp     short loc_18001728C
0x18001728a  xor     ebx, ebx
0x18001728c  test    r15, r15
0x18001728f  jz      short loc_18001729A
0x180017291  mov     rcx, r15; Object
0x180017294  call    cs:__imp_I_RpcFree
0x18001729a  mov     rax, [rbp+57h+Src]
0x18001729e  test    rax, rax
0x1800172a1  jz      short loc_1800172AC
0x1800172a3  mov     rcx, rax; Object
0x1800172a6  call    cs:__imp_I_RpcFree
0x1800172ac  test    r12, r12
0x1800172af  jz      short loc_1800172BA
0x1800172b1  mov     rcx, r12; Object
0x1800172b4  call    cs:__imp_I_RpcFree
0x1800172ba  test    r13, r13
0x1800172bd  jz      short loc_1800172C8
0x1800172bf  mov     rcx, r13; Object
0x1800172c2  call    cs:__imp_I_RpcFree
0x1800172c8  test    rsi, rsi
0x1800172cb  jz      short loc_1800172DB
0x1800172cd  cmp     rsi, rdi
0x1800172d0  jz      short loc_1800172DB
0x1800172d2  mov     rcx, rsi; Object
0x1800172d5  call    cs:__imp_I_RpcFree
0x1800172db  mov     eax, ebx
0x1800172dd  mov     rcx, [rbp+57h+var_40]
0x1800172e1  xor     rcx, rsp; StackCookie
0x1800172e4  call    __security_check_cookie
0x1800172e9  mov     rbx, [rsp+0C0h+arg_10]
0x1800172f1  add     rsp, 90h
0x1800172f8  pop     r15
0x1800172fa  pop     r14
0x1800172fc  pop     r13
0x1800172fe  pop     r12
0x180017300  pop     rdi
0x180017301  pop     rsi
0x180017302  pop     rbp
0x180017303  retn
```
