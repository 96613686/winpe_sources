# CClientLibrary::SessionCreate(WDS_CRED *,tagWDS_ENDPOINT *,tagWDS_ENDPOINT *,void * *)

- ea: `0x180009b30`
- end: `0x180009d6f`
- name: `?SessionCreate@CClientLibrary@@QEAAKPEAUWDS_CRED@@PEAUtagWDS_ENDPOINT@@1PEAPEAX@Z`
- size: `575`
- prototype: `unsigned int __fastcall(CClientLibrary *__hidden this, struct WDS_CRED *, struct tagWDS_ENDPOINT *Src, struct tagWDS_ENDPOINT *, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ceb0`
- `0x18000d0f0`

## callees

- `0x1800017d8`
- `0x1800026c4`
- `0x18000726c`
- `0x1800077f4`
- `0x180009b30`
- `0x18000bd5c`
- `0x18000d6d2`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009d3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009d3c`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180009cd3`
- `WdsCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180009cd3`

## pseudocode

```c
__int64 __fastcall CClientLibrary::SessionCreate(
        CClientLibrary *this,
        struct WDS_CRED *a2,
        struct tagWDS_ENDPOINT *Src,
        struct tagWDS_ENDPOINT *a4,
        void **a5)
{
  _DWORD *v6; // rbx
  struct WDS_CRED *v8; // r12
  unsigned int v10; // esi
  unsigned int v11; // r10d
  int v12; // ecx
  __int64 v13; // rdx
  _DWORD *v14; // rax
  unsigned int *v15; // r14
  CClientLibrary *v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r9

  v6 = 0;
  v8 = a2;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 10, 0) )
    return 5023;
  v11 = 87;
  if ( a4 && *(_DWORD *)a4 == 1052 && (!Src || *(_DWORD *)Src == 1052 && !*((_DWORD *)Src + 1) && !*((_DWORD *)a4 + 1)) )
  {
    v12 = *((_DWORD *)a4 + 1);
    if ( !v12 )
    {
      if ( !*((_WORD *)a4 + 6) )
        goto LABEL_19;
      goto LABEL_17;
    }
    if ( v12 == 1 )
    {
      if ( *((_WORD *)a4 + 14) )
      {
        a2 = (struct WDS_CRED *)*((unsigned int *)a4 + 2);
        if ( (_DWORD)a2 )
        {
          if ( ((unsigned __int8)a2 & 3) != 3 && ((unsigned int)a2 & 0xFFFFFFFC) == 0 )
          {
            if ( ((unsigned __int8)a2 & 2) == 0 )
            {
LABEL_18:
              v11 = 0;
              goto LABEL_19;
            }
LABEL_17:
            if ( v8 )
              goto LABEL_19;
            goto LABEL_18;
          }
        }
      }
    }
  }
LABEL_19:
  v10 = ElValidateWin32(v11, a2, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1023);
  if ( !(unsigned int)ElValidateWin32(v10, v13, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1025) )
  {
    if ( !a5 )
      return 87;
    *a5 = 0;
    v14 = operator new(0x868u, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v14;
    if ( !v14 )
      return 8;
    memset_0(v14, 0, 0x868u);
    if ( Src )
    {
      memmove_0(v6, Src, 0x41Cu);
      v15 = (unsigned int *)((char *)a4 + 4);
    }
    else
    {
      v15 = (unsigned int *)((char *)a4 + 4);
      if ( !*((_DWORD *)a4 + 1) )
      {
        v6[1] = 0;
        v6[8] = *((_DWORD *)a4 + 8);
      }
    }
    memmove_0(v6 + 263, a4, 0x41Cu);
    v16 = (CClientLibrary *)*v15;
    if ( (_DWORD)v16 )
    {
      if ( (_DWORD)v16 != 1 )
      {
        WdsAssert("base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 0x43Au, "0", 1, 0);
        goto LABEL_33;
      }
      v18 = CClientLibrary::InitializeRpcSession(v16, (struct Session *)v6, v8);
      v20 = 1078;
    }
    else
    {
      v18 = CClientLibrary::InitializeUdpSession(this, (struct Session *)v6);
      v20 = 1074;
    }
    v10 = ElValidateWin32(v18, v19, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", v20);
LABEL_33:
    if ( !(unsigned int)ElValidateWin32(v10, v17, "base\\eco\\wds\\wdscsl\\client\\clientlib.cpp", 1085) )
      *a5 = v6;
  }
  if ( v10 && v6 )
    operator delete(v6);
  return v10;
}

```

## disassembly

```asm
0x180009b30  mov     [rsp+arg_0], rbx
0x180009b35  mov     [rsp+arg_8], rbp
0x180009b3a  mov     [rsp+arg_10], rsi
0x180009b3f  push    rdi
0x180009b40  push    r12
0x180009b42  push    r13
0x180009b44  push    r14
0x180009b46  push    r15
0x180009b48  sub     rsp, 30h
0x180009b4c  xor     r14d, r14d
0x180009b4f  mov     rdi, r9
0x180009b52  mov     ebx, r14d
0x180009b55  mov     eax, r14d
0x180009b58  mov     rbp, r8
0x180009b5b  mov     r12, rdx
0x180009b5e  mov     r13, rcx
0x180009b61  lock xadd [rcx+28h], eax
0x180009b66  test    eax, eax
0x180009b68  jnz     short loc_180009B74
0x180009b6a  mov     esi, 139Fh
0x180009b6f  jmp     loc_180009D48
0x180009b74  mov     r10d, 57h ; 'W'
0x180009b7a  test    rdi, rdi
0x180009b7d  jz      short loc_180009BEB
0x180009b7f  cmp     dword ptr [r9], 41Ch
0x180009b86  jnz     short loc_180009BEB
0x180009b88  test    rbp, rbp
0x180009b8b  jz      short loc_180009BA2
0x180009b8d  cmp     dword ptr [r8], 41Ch
0x180009b94  jnz     short loc_180009BEB
0x180009b96  cmp     [r8+4], r14d
0x180009b9a  jnz     short loc_180009BEB
0x180009b9c  cmp     [r9+4], r14d
0x180009ba0  jnz     short loc_180009BEB
0x180009ba2  mov     ecx, [r9+4]
0x180009ba6  test    ecx, ecx
0x180009ba8  jz      short loc_180009BDC
0x180009baa  cmp     ecx, 1
0x180009bad  jnz     short loc_180009BEB
0x180009baf  cmp     [r9+1Ch], r14w
0x180009bb4  jz      short loc_180009BEB
0x180009bb6  mov     edx, [r9+8]
0x180009bba  test    edx, edx
0x180009bbc  jz      short loc_180009BEB
0x180009bbe  mov     eax, edx
0x180009bc0  and     eax, 3
0x180009bc3  cmp     al, 3
0x180009bc5  setnz   cl
0x180009bc8  test    edx, 0FFFFFFFCh
0x180009bce  setz    al
0x180009bd1  test    al, cl
0x180009bd3  jz      short loc_180009BEB
0x180009bd5  test    dl, 2
0x180009bd8  jz      short loc_180009BE8
0x180009bda  jmp     short loc_180009BE3
0x180009bdc  cmp     [r9+0Ch], r14w
0x180009be1  jz      short loc_180009BEB
0x180009be3  test    r12, r12
0x180009be6  jnz     short loc_180009BEB
0x180009be8  mov     r10d, r14d
0x180009beb  mov     r9d, 3FFh
0x180009bf1  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009bf8  mov     ecx, r10d
0x180009bfb  call    ElValidateWin32
0x180009c00  mov     r9d, 401h
0x180009c06  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009c0d  mov     ecx, eax
0x180009c0f  mov     esi, eax
0x180009c11  call    ElValidateWin32
0x180009c16  test    eax, eax
0x180009c18  jnz     loc_180009D30
0x180009c1e  mov     r15, [rsp+58h+arg_20]
0x180009c26  test    r15, r15
0x180009c29  jnz     short loc_180009C33
0x180009c2b  lea     esi, [rax+57h]
0x180009c2e  jmp     loc_180009D48
0x180009c33  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009c3a  mov     [r15], r14
0x180009c3d  mov     ecx, 868h; unsigned __int64
0x180009c42  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009c47  mov     rbx, rax
0x180009c4a  test    rax, rax
0x180009c4d  jz      loc_180009D68
0x180009c53  xor     edx, edx; Val
0x180009c55  mov     r8d, 868h; Size
0x180009c5b  mov     rcx, rax; void *
0x180009c5e  call    memset_0
0x180009c63  test    rbp, rbp
0x180009c66  jz      short loc_180009C7F
0x180009c68  mov     r8d, 41Ch; Size
0x180009c6e  mov     rdx, rbp; Src
0x180009c71  mov     rcx, rbx; void *
0x180009c74  call    memmove_0
0x180009c79  lea     r14, [rdi+4]
0x180009c7d  jmp     short loc_180009C93
0x180009c7f  lea     r14, [rdi+4]
0x180009c83  cmp     dword ptr [r14], 0
0x180009c87  jnz     short loc_180009C93
0x180009c89  and     dword ptr [rbx+4], 0
0x180009c8d  mov     eax, [rdi+20h]
0x180009c90  mov     [rbx+20h], eax
0x180009c93  lea     rcx, [rbx+41Ch]; void *
0x180009c9a  mov     r8d, 41Ch; Size
0x180009ca0  mov     rdx, rdi; Src
0x180009ca3  call    memmove_0
0x180009ca8  mov     ecx, [r14]; this
0x180009cab  xor     r14d, r14d
0x180009cae  test    ecx, ecx
0x180009cb0  jz      short loc_180009CF4
0x180009cb2  cmp     ecx, 1
0x180009cb5  jz      short loc_180009CE1
0x180009cb7  lea     r9d, [r14+1]
0x180009cbb  mov     [rsp+58h+var_38], r14d
0x180009cc0  lea     r8, a0; "0"
0x180009cc7  mov     edx, 43Ah
0x180009ccc  lea     rcx, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009cd3  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180009cda  nop     dword ptr [rax+rax+00h]
0x180009cdf  jmp     short loc_180009D15
0x180009ce1  mov     r8, r12; struct WDS_CRED *
0x180009ce4  mov     rdx, rbx; struct Session *
0x180009ce7  call    ?InitializeRpcSession@CClientLibrary@@AEAAKPEAUSession@1@PEAUWDS_CRED@@@Z; CClientLibrary::InitializeRpcSession(CClientLibrary::Session *,WDS_CRED *)
0x180009cec  mov     r9d, 436h
0x180009cf2  jmp     short loc_180009D05
0x180009cf4  mov     rdx, rbx; struct Session *
0x180009cf7  mov     rcx, r13; this
0x180009cfa  call    ?InitializeUdpSession@CClientLibrary@@AEAAKPEAUSession@1@@Z; CClientLibrary::InitializeUdpSession(CClientLibrary::Session *)
0x180009cff  mov     r9d, 432h
0x180009d05  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009d0c  mov     ecx, eax
0x180009d0e  call    ElValidateWin32
0x180009d13  mov     esi, eax
0x180009d15  mov     r9d, 43Dh
0x180009d1b  lea     r8, aBaseEcoWdsWdsc_0; "base\\eco\\wds\\wdscsl\\client\\clientl"...
0x180009d22  mov     ecx, esi
0x180009d24  call    ElValidateWin32
0x180009d29  test    eax, eax
0x180009d2b  jnz     short loc_180009D30
0x180009d2d  mov     [r15], rbx
0x180009d30  test    esi, esi
0x180009d32  jz      short loc_180009D48
0x180009d34  test    rbx, rbx
0x180009d37  jz      short loc_180009D48
0x180009d39  mov     rcx, rbx
0x180009d3c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009d43  nop     dword ptr [rax+rax+00h]
0x180009d48  mov     rbx, [rsp+58h+arg_0]
0x180009d4d  mov     eax, esi
0x180009d4f  mov     rsi, [rsp+58h+arg_10]
0x180009d54  mov     rbp, [rsp+58h+arg_8]
0x180009d59  add     rsp, 30h
0x180009d5d  pop     r15
0x180009d5f  pop     r14
0x180009d61  pop     r13
0x180009d63  pop     r12
0x180009d65  pop     rdi
0x180009d66  retn
0x180009d68  mov     esi, 8
0x180009d6d  jmp     short loc_180009D48
```
