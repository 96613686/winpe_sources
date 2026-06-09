# CTftpFileReader::MoveRequestToSharedReader(CTptReadFile * *)

- ea: `0x1800091a4`
- end: `0x1800092cf`
- name: `?MoveRequestToSharedReader@CTftpFileReader@@AEAAKPEAPEAVCTptReadFile@@@Z`
- size: `299`
- prototype: `__int64 __fastcall(CTftpFileReader *this, struct CTptReadFile **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180006c90`
- `0x18000710c`

## callees

- `0x1800057f8`
- `0x1800091a4`
- `0x18000a960`
- `0x18003ce78`
- `0x1800607e0`
- `0x180060e5a`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800091c9`
- `KERNEL32!EnterCriticalSection` at `0x1800091c9`
- `KERNEL32!LeaveCriticalSection` at `0x1800092a6`
- `KERNEL32!LeaveCriticalSection` at `0x1800092a6`
- `WDSSRV!WdsQueueWorkItem` at `0x18000924b`
- `WDSSRV!WdsQueueWorkItem` at `0x18000924b`

## string_xrefs

- `0x18000925d`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x180009281`: `CTftpFileReader::MoveRequestToSharedReader: Queued a close buffer workitem for file: %s`

## pseudocode

```c
__int64 __fastcall CTftpFileReader::MoveRequestToSharedReader(CTftpFileReader *this, struct CTptReadFile **a2)
{
  _QWORD *v4; // rcx
  __int64 i; // r8
  __int64 v6; // r14
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  unsigned int v9; // edi
  const char *v10; // rdx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v4 = (_QWORD *)((char *)this + 96);
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 27); i = (unsigned int)(i + 1) )
  {
    if ( *a2 == *(struct CTptReadFile **)(*v4 + 8 * i) )
      break;
  }
  CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(v4);
  v6 = (__int64)*a2;
  *a2 = (struct CTptReadFile *)*((_QWORD *)this + 11);
  v7 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x40u);
    v8[8] = 1;
    *((_QWORD *)v8 + 5) = this;
    *((_QWORD *)v8 + 7) = v6;
    v9 = WdsQueueWorkItem(v8);
    if ( !ElValidateWin32(v9, v10, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x2F2u) )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(
          0x20000u,
          L"CTftpFileReader::MoveRequestToSharedReader: Queued a close buffer workitem for file: %s",
          *((_QWORD *)this + 9));
      v8 = 0;
    }
    if ( v8 )
      operator delete(v8);
  }
  else
  {
    v9 = 8;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return v9;
}

```

## disassembly

```asm
0x1800091a4  mov     rax, rsp
0x1800091a7  mov     [rax+8], rbx
0x1800091ab  mov     [rax+10h], rbp
0x1800091af  mov     [rax+18h], rsi
0x1800091b3  mov     [rax+20h], rdi
0x1800091b7  push    r14
0x1800091b9  sub     rsp, 20h
0x1800091bd  mov     rsi, rcx
0x1800091c0  mov     rdi, rdx
0x1800091c3  add     rcx, 8; lpCriticalSection
0x1800091c7  xor     ebx, ebx
0x1800091c9  call    cs:__imp_EnterCriticalSection
0x1800091d0  nop     dword ptr [rax+rax+00h]
0x1800091d5  mov     r9, [rdi]
0x1800091d8  lea     rcx, [rsi+60h]
0x1800091dc  xor     r8d, r8d
0x1800091df  cmp     [rcx+0Ch], ebx
0x1800091e2  jbe     short loc_1800091FB
0x1800091e4  mov     rdx, [rcx]
0x1800091e7  cmp     r9, [rdx+r8*8]
0x1800091eb  jz      short loc_1800091F8
0x1800091ed  inc     r8d
0x1800091f0  cmp     r8d, [rcx+0Ch]
0x1800091f4  jb      short loc_1800091E7
0x1800091f6  jmp     short loc_1800091FB
0x1800091f8  mov     ebx, r8d
0x1800091fb  mov     edx, ebx
0x1800091fd  call    ?RemoveItem@?$CDynArray@PEAVCEndpointSessionMapEntry@@VCDeallocateNone@@@@QEAAKK@Z; CDynArray<CEndpointSessionMapEntry *,CDeallocateNone>::RemoveItem(ulong)
0x180009202  mov     r14, [rdi]
0x180009205  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000920c  mov     rax, [rsi+58h]
0x180009210  mov     [rdi], rax
0x180009213  mov     edi, 40h ; '@'
0x180009218  mov     ecx, edi; unsigned __int64
0x18000921a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000921f  mov     rbx, rax
0x180009222  test    rax, rax
0x180009225  jnz     short loc_18000922C
0x180009227  lea     edi, [rax+8]
0x18000922a  jmp     short loc_1800092A2
0x18000922c  mov     r8, rdi; Size
0x18000922f  xor     edx, edx; Val
0x180009231  mov     rcx, rbx; void *
0x180009234  call    memset_0
0x180009239  mov     rcx, rbx
0x18000923c  mov     dword ptr [rbx+20h], 1
0x180009243  mov     [rbx+28h], rsi
0x180009247  mov     [rbx+38h], r14
0x18000924b  call    cs:__imp_WdsQueueWorkItem
0x180009252  nop     dword ptr [rax+rax+00h]
0x180009257  mov     r9d, 2F2h; unsigned int
0x18000925d  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180009264  mov     ecx, eax; unsigned int
0x180009266  mov     edi, eax
0x180009268  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000926d  test    eax, eax
0x18000926f  jnz     short loc_180009295
0x180009271  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180009278  test    rax, rax
0x18000927b  jz      short loc_180009293
0x18000927d  mov     r8, [rsi+48h]
0x180009281  lea     rdx, aCtftpfilereade_2; "CTftpFileReader::MoveRequestToSharedRea"...
0x180009288  mov     ecx, 20000h
0x18000928d  call    cs:__guard_dispatch_icall_fptr
0x180009293  xor     ebx, ebx
0x180009295  test    rbx, rbx
0x180009298  jz      short loc_1800092A2
0x18000929a  mov     rcx, rbx; void *
0x18000929d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800092a2  lea     rcx, [rsi+8]; lpCriticalSection
0x1800092a6  call    cs:__imp_LeaveCriticalSection
0x1800092ad  nop     dword ptr [rax+rax+00h]
0x1800092b2  mov     rbx, [rsp+28h+arg_0]
0x1800092b7  mov     eax, edi
0x1800092b9  mov     rdi, [rsp+28h+arg_18]
0x1800092be  mov     rbp, [rsp+28h+arg_8]
0x1800092c3  mov     rsi, [rsp+28h+arg_10]
0x1800092c8  add     rsp, 20h
0x1800092cc  pop     r14
0x1800092ce  retn
```
