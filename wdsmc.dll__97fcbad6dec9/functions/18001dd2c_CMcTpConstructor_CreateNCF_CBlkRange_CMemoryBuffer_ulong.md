# CMcTpConstructor::CreateNCF(CBlkRange *,CMemoryBuffer * *,ulong,...)

- ea: `0x18001dd2c`
- end: `0x18001df3b`
- name: `?CreateNCF@CMcTpConstructor@@QEAAKPEAVCBlkRange@@PEAPEAVCMemoryBuffer@@KZZ`
- size: `527`
- prototype: `unsigned int(CMcTpConstructor *__hidden this, struct CBlkRange *, struct CMemoryBuffer **, unsigned int, ...)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180013c10`

## callees

- `0x180008f4c`
- `0x18001c2ac`
- `0x18001d4f4`
- `0x18001dd2c`
- `0x180020258`
- `0x180023b28`
- `0x1800247d4`
- `0x180025850`
- `0x180026d70`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18001de14`
- `WS2_32!__imp_htonl` at `0x18001de14`
- `WS2_32!__imp_htons` at `0x18001de8d`
- `WS2_32!__imp_htons` at `0x18001de8d`

## pseudocode

```c
__int64 CMcTpConstructor::CreateNCF(
        CMcTpConstructor *this,
        struct CBlkRange *a2,
        struct CMemoryBuffer **a3,
        unsigned int a4,
        ...)
{
  unsigned int v4; // r15d
  va_list v7; // rcx
  struct CMemoryBuffer *v8; // rdi
  __int64 v9; // r14
  unsigned int v10; // ebx
  int v11; // r8d
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // r8d
  bool v15; // cf
  unsigned int v16; // ecx
  unsigned int Options; // ebx
  unsigned int v18; // r8d
  struct CMemoryBuffer *v19; // rax
  struct CMemoryBuffer *v20; // rsi
  _WORD *v21; // rax
  __int64 v22; // r12
  u_long v23; // eax
  LONGLONG v24; // rax
  u_short v25; // ax
  int v26; // r9d
  const char *v27; // rdx
  va_list va; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va, a4);
  v4 = *((_DWORD *)a2 + 256);
  va_copy(v7, va);
  v8 = 0;
  v9 = 0;
  v10 = 2;
  if ( v4 > 0x40 )
    v4 = 64;
  v11 = 16 * v4;
  if ( a4 )
  {
    v12 = a4;
    do
    {
      v10 += *((_DWORD *)v7 + 2) + 4;
      v7 += 24;
      --v12;
    }
    while ( v12 );
  }
  v13 = v11 + 15;
  v14 = v10 + v11 + 15;
  v15 = v14 < v13;
  if ( v14 < v13 || (v16 = v14, v18 = v14 + *((_DWORD *)this + 25), v15 = v18 < v16) )
  {
    Options = v15 ? 0x216 : 0;
  }
  else
  {
    if ( v18 > 0xFFFF )
      return 111;
    v19 = TptMemoryBufferAllocate(v18);
    v20 = v19;
    if ( !v19 )
      return 8;
    v21 = (_WORD *)*((_QWORD *)v19 + 5);
    *v21 = 17495;
    *(_WORD *)((char *)v21 + 3) = 0;
    v22 = *((_QWORD *)v20 + 5) + *((unsigned int *)this + 25);
    v23 = htonl(*((_DWORD *)this + 1));
    *(_BYTE *)(v22 + 4) = 10;
    *(_DWORD *)v22 = v23;
    v24 = CStopwatch::CurrentMs((CMcTpConstructor *)((char *)this + 104));
    *(_QWORD *)(v22 + 5) = CNetworkAddress::HostToNetworkByteOrder(v24);
    Options = CMcTpOptions::CreateOptions(a4, va, (struct _WDSMCTP_OPTIONS *)(v22 + 16 * v4 + 15LL), v10);
    if ( Options )
      goto LABEL_17;
    v8 = v20;
    v9 = v22;
  }
  v20 = v8;
  if ( Options )
  {
LABEL_17:
    if ( v20 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v20 + 8LL))(v20);
LABEL_26:
    if ( v8 )
      (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v8 + 8LL))(v8);
    return Options;
  }
  v25 = htons(v4);
  *(_WORD *)(v9 + 13) = v25;
  Options = CBlkRange::Copy(a2, (struct _WDSMC_BLOCK_RANGE *)(v9 + 15), v25, v26);
  if ( Options )
    goto LABEL_26;
  Options = CMcTpConstructor::ServerSecurePacket(this, v8);
  if ( !ElValidateWin32(Options, v27, "base\\eco\\wds\\transport\\lib\\mctpconstructor.cpp", 0xA2Bu) )
  {
    if ( g_ErrLibTraceFunctionEx )
      g_ErrLibTraceFunctionEx(
        0x400000u,
        L"MCTPConstruct[NCF]: Session=0x%x, RangeCount=%u",
        *((unsigned int *)this + 1),
        *((unsigned int *)a2 + 256));
    *a3 = v8;
  }
  if ( Options )
    goto LABEL_26;
  return Options;
}

```

## disassembly

```asm
0x18001dd2c  mov     r11, rsp
0x18001dd2f  mov     [r11+20h], r9d
0x18001dd33  mov     [r11+18h], r8
0x18001dd37  mov     [r11+10h], rdx
0x18001dd3b  push    rbx
0x18001dd3c  push    rbp
0x18001dd3d  push    rsi
0x18001dd3e  push    rdi
0x18001dd3f  push    r12
0x18001dd41  push    r13
0x18001dd43  push    r14
0x18001dd45  push    r15
0x18001dd47  sub     rsp, 48h
0x18001dd4b  mov     r15d, [rdx+400h]
0x18001dd52  xor     r12d, r12d
0x18001dd55  mov     rbp, rcx
0x18001dd58  mov     [r11-58h], r12
0x18001dd5c  mov     r13d, r9d
0x18001dd5f  lea     rcx, [r11+28h]
0x18001dd63  mov     edi, r12d
0x18001dd66  mov     r14d, r12d
0x18001dd69  lea     eax, [r12+40h]
0x18001dd6e  cmp     r15d, eax
0x18001dd71  lea     ebx, [rax-3Eh]
0x18001dd74  cmova   r15d, eax
0x18001dd78  mov     r8d, r15d
0x18001dd7b  shl     r8d, 4
0x18001dd7f  mov     [rsp+88h+var_58], r8d
0x18001dd84  test    r9d, r9d
0x18001dd87  jz      short loc_18001DD9C
0x18001dd89  mov     edx, r13d
0x18001dd8c  add     ebx, 4
0x18001dd8f  add     ebx, [rcx+8]
0x18001dd92  lea     rcx, [rcx+18h]
0x18001dd96  sub     rdx, 1
0x18001dd9a  jnz     short loc_18001DD8C
0x18001dd9c  lea     eax, [r8+0Fh]
0x18001dda0  or      edx, 0FFFFFFFFh
0x18001dda3  lea     r8d, [rbx+rax]
0x18001dda7  mov     ecx, edx
0x18001dda9  cmp     r8d, eax
0x18001ddac  cmovnb  ecx, r8d
0x18001ddb0  jnb     short loc_18001DDBF
0x18001ddb2  sbb     ebx, ebx
0x18001ddb4  and     ebx, 216h
0x18001ddba  jmp     loc_18001DE65
0x18001ddbf  mov     r8d, [rbp+64h]
0x18001ddc3  add     r8d, ecx
0x18001ddc6  cmp     r8d, ecx
0x18001ddc9  cmovnb  edx, r8d
0x18001ddcd  jb      short loc_18001DDB2
0x18001ddcf  cmp     edx, 0FFFFh
0x18001ddd5  jbe     short loc_18001DDE1
0x18001ddd7  mov     ebx, 6Fh ; 'o'
0x18001dddc  jmp     loc_18001DF28
0x18001dde1  mov     ecx, edx; unsigned int
0x18001dde3  call    ?TptMemoryBufferAllocate@@YAPEAVCMemoryBuffer@@K@Z; TptMemoryBufferAllocate(ulong)
0x18001dde8  mov     rsi, rax
0x18001ddeb  test    rax, rax
0x18001ddee  jnz     short loc_18001DDF8
0x18001ddf0  lea     ebx, [rax+8]
0x18001ddf3  jmp     loc_18001DF28
0x18001ddf8  mov     rax, [rax+28h]
0x18001ddfc  mov     ecx, 4457h
0x18001de01  mov     [rax], cx
0x18001de04  mov     [rax+3], r12w
0x18001de09  mov     r12d, [rbp+64h]
0x18001de0d  mov     ecx, [rbp+4]; hostlong
0x18001de10  add     r12, [rsi+28h]
0x18001de14  call    cs:__imp_htonl
0x18001de1a  lea     rcx, [rbp+68h]; this
0x18001de1e  mov     byte ptr [r12+4], 0Ah
0x18001de24  mov     [r12], eax
0x18001de28  call    ?CurrentMs@CStopwatch@@QEAA_KXZ; CStopwatch::CurrentMs(void)
0x18001de2d  mov     rcx, rax; unsigned __int64
0x18001de30  call    ?HostToNetworkByteOrder@CNetworkAddress@@SA_K_K@Z; CNetworkAddress::HostToNetworkByteOrder(unsigned __int64)
0x18001de35  mov     r8d, [rsp+88h+var_58]
0x18001de3a  lea     rdx, [rsp+88h+arg_20]; char *
0x18001de42  add     r8, 0Fh
0x18001de46  mov     [r12+5], rax
0x18001de4b  add     r8, r12; struct _WDSMCTP_OPTIONS *
0x18001de4e  mov     r9d, ebx; unsigned int
0x18001de51  mov     ecx, r13d; unsigned int
0x18001de54  call    ?CreateOptions@CMcTpOptions@@SAKKPEADPEAU_WDSMCTP_OPTIONS@@K@Z; CMcTpOptions::CreateOptions(ulong,char *,_WDSMCTP_OPTIONS *,ulong)
0x18001de59  mov     ebx, eax
0x18001de5b  test    eax, eax
0x18001de5d  jnz     short loc_18001DE6C
0x18001de5f  mov     rdi, rsi
0x18001de62  mov     r14, r12
0x18001de65  mov     rsi, rdi
0x18001de68  test    ebx, ebx
0x18001de6a  jz      short loc_18001DE89
0x18001de6c  test    rsi, rsi
0x18001de6f  jz      short loc_18001DE81
0x18001de71  mov     rax, [rsi]
0x18001de74  mov     rcx, rsi
0x18001de77  mov     rax, [rax+8]
0x18001de7b  call    cs:__guard_dispatch_icall_fptr
0x18001de81  test    ebx, ebx
0x18001de83  jnz     loc_18001DF13
0x18001de89  movzx   ecx, r15w; hostshort
0x18001de8d  call    cs:__imp_htons
0x18001de93  mov     rsi, [rsp+88h+arg_8]
0x18001de9b  lea     rdx, [r14+0Fh]; struct _WDSMC_BLOCK_RANGE *
0x18001de9f  movzx   r8d, ax; unsigned int
0x18001dea3  mov     rcx, rsi; this
0x18001dea6  mov     [r14+0Dh], r8w
0x18001deab  call    ?Copy@CBlkRange@@QEBAKPEAU_WDSMC_BLOCK_RANGE@@KH@Z; CBlkRange::Copy(_WDSMC_BLOCK_RANGE *,ulong,int)
0x18001deb0  mov     ebx, eax
0x18001deb2  test    eax, eax
0x18001deb4  jnz     short loc_18001DF13
0x18001deb6  mov     rdx, rdi; struct CMemoryBuffer *
0x18001deb9  mov     rcx, rbp; this
0x18001debc  call    ?ServerSecurePacket@CMcTpConstructor@@AEAAKPEAVCMemoryBuffer@@@Z; CMcTpConstructor::ServerSecurePacket(CMemoryBuffer *)
0x18001dec1  mov     r9d, 0A2Bh; unsigned int
0x18001dec7  lea     r8, aBaseEcoWdsTran_17; "base\\eco\\wds\\transport\\lib\\mctpcon"...
0x18001dece  mov     ecx, eax; unsigned int
0x18001ded0  mov     ebx, eax
0x18001ded2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001ded7  test    eax, eax
0x18001ded9  jnz     short loc_18001DF0F
0x18001dedb  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18001dee2  test    rax, rax
0x18001dee5  jz      short loc_18001DF04
0x18001dee7  mov     r9d, [rsi+400h]
0x18001deee  lea     rdx, aMctpconstructN; "MCTPConstruct[NCF]: Session=0x%x, Range"...
0x18001def5  mov     r8d, [rbp+4]
0x18001def9  mov     ecx, 400000h
0x18001defe  call    cs:__guard_dispatch_icall_fptr
0x18001df04  mov     rax, [rsp+88h+arg_10]
0x18001df0c  mov     [rax], rdi
0x18001df0f  test    ebx, ebx
0x18001df11  jz      short loc_18001DF28
0x18001df13  test    rdi, rdi
0x18001df16  jz      short loc_18001DF28
0x18001df18  mov     rax, [rdi]
0x18001df1b  mov     rcx, rdi
0x18001df1e  mov     rax, [rax+8]
0x18001df22  call    cs:__guard_dispatch_icall_fptr
0x18001df28  mov     eax, ebx
0x18001df2a  add     rsp, 48h
0x18001df2e  pop     r15
0x18001df30  pop     r14
0x18001df32  pop     r13
0x18001df34  pop     r12
0x18001df36  pop     rdi
0x18001df37  pop     rsi
0x18001df38  pop     rbp
0x18001df39  pop     rbx
0x18001df3a  retn
```
