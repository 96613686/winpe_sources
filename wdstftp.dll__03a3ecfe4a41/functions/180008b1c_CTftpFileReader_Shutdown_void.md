# CTftpFileReader::Shutdown(void)

- ea: `0x180008b1c`
- end: `0x180008d79`
- name: `?Shutdown@CTftpFileReader@@QEAAKXZ`
- size: `605`
- prototype: `__int64 __fastcall(CTftpFileReader *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180009614`
- `0x1800098a0`
- `0x180009d20`

## callees

- `0x180005850`
- `0x180008b1c`
- `0x18000a960`
- `0x18000c168`
- `0x18000d66c`
- `0x18000d84c`
- `0x18003c084`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180008b50`
- `KERNEL32!EnterCriticalSection` at `0x180008b50`
- `KERNEL32!LeaveCriticalSection` at `0x180008bda`
- `KERNEL32!LeaveCriticalSection` at `0x180008bda`
- `KERNEL32!DeleteCriticalSection` at `0x180008c32`
- `KERNEL32!DeleteCriticalSection` at `0x180008ce8`
- `KERNEL32!DeleteCriticalSection` at `0x180008c32`
- `KERNEL32!DeleteCriticalSection` at `0x180008ce8`

## pseudocode

```c
__int64 __fastcall CTftpFileReader::Shutdown(CTftpFileReader *this)
{
  __int64 v2; // rdi
  void *v3; // rcx
  unsigned int i; // ebp
  void *v5; // rcx
  int v6; // ecx
  unsigned __int64 v7; // rbx
  __int64 v8; // rbx
  unsigned int v9; // ebp
  unsigned int v10; // r15d
  void *v11; // rdi
  __int64 *v12; // r14
  __int64 v13; // rsi
  int v14; // ecx
  unsigned __int64 v15; // rbx
  __int64 v16; // rbx
  __int64 v18; // [rsp+20h] [rbp-58h]
  __int64 v19; // [rsp+20h] [rbp-58h]
  __int64 v20; // [rsp+20h] [rbp-58h]
  void *v21; // [rsp+30h] [rbp-48h] BYREF
  __int64 v22; // [rsp+38h] [rbp-40h]

  v21 = 0;
  v22 = 0;
  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 9) = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 0) )
  {
    v2 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
    _InterlockedExchange((volatile __int32 *)this + 14, 0);
  }
  for ( i = 0; i < *((_DWORD *)this + 27); ++i )
    CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(&v21);
  v5 = (void *)*((_QWORD *)this + 12);
  if ( v5 )
  {
    operator delete(v5);
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
  }
  *(_QWORD *)((char *)this + 60) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( v2 )
  {
    v6 = *(_DWORD *)(v2 + 124);
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        v7 = 0;
LABEL_16:
        CTptReadFile::Shutdown((LPCRITICAL_SECTION)v2);
        CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(v2 + 168);
        CWIMFile::Shutdown((CWIMFile *)(v2 + 72));
        DeleteCriticalSection((LPCRITICAL_SECTION)v2);
        operator delete((void *)v2);
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 4, 1, 1);
        LODWORD(v19) = v7 >> 10;
        CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 5, 1, v19);
        goto LABEL_17;
      }
      v8 = *(unsigned int *)(v2 + 160);
    }
    else
    {
      v8 = *(unsigned int *)(v2 + 108);
    }
    v7 = *(unsigned int *)(v2 + 104) * v8;
    goto LABEL_16;
  }
LABEL_17:
  v9 = HIDWORD(v22);
  v10 = 0;
  v11 = v21;
  if ( HIDWORD(v22) )
  {
    v12 = (__int64 *)v21;
    while ( 1 )
    {
      v13 = *v12;
      *v12 = 0;
      v14 = *(_DWORD *)(v13 + 124);
      if ( !v14 )
        break;
      if ( v14 == 1 )
      {
        v16 = *(unsigned int *)(v13 + 160);
LABEL_24:
        v15 = *(unsigned int *)(v13 + 104) * v16;
        goto LABEL_25;
      }
      v15 = 0;
LABEL_25:
      CTptReadFile::Shutdown((LPCRITICAL_SECTION)v13);
      CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(v13 + 168);
      CWIMFile::Shutdown((CWIMFile *)(v13 + 72));
      DeleteCriticalSection((LPCRITICAL_SECTION)v13);
      operator delete((void *)v13);
      LODWORD(v18) = 1;
      CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 6, 1, v18);
      LODWORD(v20) = v15 >> 10;
      CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 7, 1, v20);
      ++v10;
      ++v12;
      if ( v10 >= v9 )
        goto LABEL_26;
    }
    v16 = *(unsigned int *)(v13 + 108);
    goto LABEL_24;
  }
LABEL_26:
  if ( v11 )
    operator delete(v11);
  return 0;
}

```

## disassembly

```asm
0x180008b1c  mov     rax, rsp
0x180008b1f  mov     [rax+8], rbx
0x180008b23  mov     [rax+10h], rbp
0x180008b27  mov     [rax+18h], rsi
0x180008b2b  push    rdi
0x180008b2c  push    r12
0x180008b2e  push    r13
0x180008b30  push    r14
0x180008b32  push    r15
0x180008b34  sub     rsp, 50h
0x180008b38  xor     r12d, r12d
0x180008b3b  mov     rbx, rcx
0x180008b3e  add     rcx, 8; lpCriticalSection
0x180008b42  mov     [rax-48h], r12
0x180008b46  mov     esi, r12d
0x180008b49  mov     [rax-40h], r12
0x180008b4d  mov     edi, r12d
0x180008b50  call    cs:__imp_EnterCriticalSection
0x180008b57  nop     dword ptr [rax+rax+00h]
0x180008b5c  mov     rcx, [rbx+48h]; void *
0x180008b60  test    rcx, rcx
0x180008b63  jz      short loc_180008B6E
0x180008b65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008b6a  mov     [rbx+48h], r12
0x180008b6e  mov     eax, r12d
0x180008b71  lock xadd [rbx+38h], eax
0x180008b76  test    eax, eax
0x180008b78  jz      short loc_180008B88
0x180008b7a  mov     rdi, [rbx+58h]
0x180008b7e  mov     eax, r12d
0x180008b81  mov     [rbx+58h], r12
0x180008b85  xchg    eax, [rbx+38h]
0x180008b88  mov     ebp, r12d
0x180008b8b  mov     r13d, 1
0x180008b91  cmp     [rbx+6Ch], r12d
0x180008b95  jbe     short loc_180008BBC
0x180008b97  cmp     r12d, [rbx+6Ch]
0x180008b9b  jnb     short loc_180008BA7
0x180008b9d  mov     rax, [rbx+60h]
0x180008ba1  mov     ecx, ebp
0x180008ba3  mov     rsi, [rax+rcx*8]
0x180008ba7  mov     rdx, rsi
0x180008baa  lea     rcx, [rsp+78h+var_48]
0x180008baf  call    ?AddItem@?$CDynArray@PEAVCTptReadFile@@VCDeallocateNone@@@@QEAAKPEAVCTptReadFile@@@Z; CDynArray<CTptReadFile *,CDeallocateNone>::AddItem(CTptReadFile *)
0x180008bb4  add     ebp, r13d
0x180008bb7  cmp     ebp, [rbx+6Ch]
0x180008bba  jb      short loc_180008B9D
0x180008bbc  mov     rcx, [rbx+60h]; void *
0x180008bc0  test    rcx, rcx
0x180008bc3  jz      short loc_180008BD2
0x180008bc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008bca  mov     [rbx+60h], r12
0x180008bce  mov     [rbx+68h], r12
0x180008bd2  lea     rcx, [rbx+8]; lpCriticalSection
0x180008bd6  mov     [rbx+3Ch], r12
0x180008bda  call    cs:__imp_LeaveCriticalSection
0x180008be1  nop     dword ptr [rax+rax+00h]
0x180008be6  test    rdi, rdi
0x180008be9  jz      loc_180008C83
0x180008bef  mov     ecx, [rdi+7Ch]
0x180008bf2  test    ecx, ecx
0x180008bf4  jz      short loc_180008C08
0x180008bf6  cmp     ecx, r13d
0x180008bf9  jz      short loc_180008C00
0x180008bfb  mov     rbx, r12
0x180008bfe  jmp     short loc_180008C12
0x180008c00  mov     ebx, [rdi+0A0h]
0x180008c06  jmp     short loc_180008C0B
0x180008c08  mov     ebx, [rdi+6Ch]
0x180008c0b  mov     eax, [rdi+68h]
0x180008c0e  imul    rbx, rax
0x180008c12  mov     rcx, rdi; lpCriticalSection
0x180008c15  call    ?Shutdown@CTptReadFile@@QEAAKXZ; CTptReadFile::Shutdown(void)
0x180008c1a  lea     rcx, [rdi+0A8h]
0x180008c21  call    ??1?$CChildCount@VCTptReadFile@@@@QEAA@XZ; CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(void)
0x180008c26  lea     rcx, [rdi+48h]; this
0x180008c2a  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x180008c2f  mov     rcx, rdi; lpCriticalSection
0x180008c32  call    cs:__imp_DeleteCriticalSection
0x180008c39  nop     dword ptr [rax+rax+00h]
0x180008c3e  mov     rcx, rdi; void *
0x180008c41  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008c46  mov     r9d, r13d
0x180008c49  mov     [rsp+78h+var_58], r13d
0x180008c4e  mov     r8d, 4
0x180008c54  lea     rcx, qword_1800779F0; this
0x180008c5b  mov     edx, r13d; unsigned int
0x180008c5e  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180008c63  shr     rbx, 0Ah
0x180008c67  lea     rcx, qword_1800779F0; this
0x180008c6e  mov     r9d, r13d
0x180008c71  mov     [rsp+78h+var_58], ebx
0x180008c75  mov     r8d, 5
0x180008c7b  mov     edx, r13d; unsigned int
0x180008c7e  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180008c83  mov     ebp, [rsp+78h+var_3C]
0x180008c87  mov     r15d, r12d
0x180008c8a  mov     rdi, [rsp+78h+var_48]
0x180008c8f  test    ebp, ebp
0x180008c91  jz      loc_180008D4C
0x180008c97  mov     r14, rdi
0x180008c9a  cmp     r12d, ebp
0x180008c9d  jnb     short loc_180008CA5
0x180008c9f  mov     rsi, [r14]
0x180008ca2  mov     [r14], r12
0x180008ca5  mov     ecx, [rsi+7Ch]
0x180008ca8  test    ecx, ecx
0x180008caa  jz      short loc_180008CBE
0x180008cac  cmp     ecx, r13d
0x180008caf  jz      short loc_180008CB6
0x180008cb1  mov     rbx, r12
0x180008cb4  jmp     short loc_180008CC8
0x180008cb6  mov     ebx, [rsi+0A0h]
0x180008cbc  jmp     short loc_180008CC1
0x180008cbe  mov     ebx, [rsi+6Ch]
0x180008cc1  mov     eax, [rsi+68h]
0x180008cc4  imul    rbx, rax
0x180008cc8  mov     rcx, rsi; lpCriticalSection
0x180008ccb  call    ?Shutdown@CTptReadFile@@QEAAKXZ; CTptReadFile::Shutdown(void)
0x180008cd0  lea     rcx, [rsi+0A8h]
0x180008cd7  call    ??1?$CChildCount@VCTptReadFile@@@@QEAA@XZ; CChildCount<CTptReadFile>::~CChildCount<CTptReadFile>(void)
0x180008cdc  lea     rcx, [rsi+48h]; this
0x180008ce0  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x180008ce5  mov     rcx, rsi; lpCriticalSection
0x180008ce8  call    cs:__imp_DeleteCriticalSection
0x180008cef  nop     dword ptr [rax+rax+00h]
0x180008cf4  mov     rcx, rsi; void *
0x180008cf7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008cfc  mov     r9d, r13d
0x180008cff  mov     [rsp+78h+var_58], r13d
0x180008d04  mov     r8d, 6
0x180008d0a  lea     rcx, qword_1800779F0; this
0x180008d11  mov     edx, r13d; unsigned int
0x180008d14  mov     rsi, r12
0x180008d17  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180008d1c  shr     rbx, 0Ah
0x180008d20  lea     rcx, qword_1800779F0; this
0x180008d27  mov     r9d, r13d
0x180008d2a  mov     [rsp+78h+var_58], ebx
0x180008d2e  mov     r8d, 7
0x180008d34  mov     edx, r13d; unsigned int
0x180008d37  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180008d3c  add     r15d, r13d
0x180008d3f  add     r14, 8
0x180008d43  cmp     r15d, ebp
0x180008d46  jb      loc_180008C9F
0x180008d4c  test    rdi, rdi
0x180008d4f  jz      short loc_180008D59
0x180008d51  mov     rcx, rdi; void *
0x180008d54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008d59  lea     r11, [rsp+78h+var_28]
0x180008d5e  xor     eax, eax
0x180008d60  mov     rbx, [r11+30h]
0x180008d64  mov     rbp, [r11+38h]
0x180008d68  mov     rsi, [r11+40h]
0x180008d6c  mov     rsp, r11
0x180008d6f  pop     r15
0x180008d71  pop     r14
0x180008d73  pop     r13
0x180008d75  pop     r12
0x180008d77  pop     rdi
0x180008d78  retn
```
