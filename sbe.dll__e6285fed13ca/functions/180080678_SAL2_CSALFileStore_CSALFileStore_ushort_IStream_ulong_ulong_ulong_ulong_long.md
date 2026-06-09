# SAL2::CSALFileStore::CSALFileStore(ushort *,IStream *,ulong,ulong,ulong,ulong,long *)

- ea: `0x180080678`
- end: `0x1800807ca`
- name: `??0CSALFileStore@SAL2@@IEAA@PEAGPEAUIStream@@KKKKPEAJ@Z`
- size: `338`
- prototype: `__int64 __usercall@<rax>(SAL2::CSALFileStore *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, struct IStream *@<r8>, unsigned int@<r9d>, unsigned int, unsigned int, unsigned int, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18008035c`

## callees

- `0x180001c00`
- `0x180080678`
- `0x1800833f0`
- `0x180085dc0`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180080777`
- `KERNEL32!GetLastError` at `0x180080777`
- `KERNEL32!GetFullPathNameW` at `0x18008076d`
- `KERNEL32!GetFullPathNameW` at `0x18008076d`
- `ole32!CoCreateGuid` at `0x180080728`
- `ole32!CoCreateGuid` at `0x180080728`

## pseudocode

```c
SAL2::CSALFileStore *__fastcall SAL2::CSALFileStore::CSALFileStore(
        SAL2::CSALFileStore *this,
        LPCWSTR lpFileName,
        struct IStream *a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int *a8)
{
  SAL2 *v9; // rsi
  HRESULT v10; // eax
  unsigned __int16 *v11; // rdx
  unsigned __int16 *v12; // r9
  signed int File; // eax
  int FileDir; // eax
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF

  *(_QWORD *)this = &SAL2::CSALFileStore::`vftable';
  *((_DWORD *)this + 269) = a6;
  *((_DWORD *)this + 270) = a5;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = -1;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 268) = a4;
  *((_DWORD *)this + 271) = 1610612736;
  if ( *a8 >= 0 )
  {
    v9 = (SAL2::CSALFileStore *)((char *)this + 32);
    if ( !a3 )
    {
      *(_QWORD *)&pguid.Data1 = 0;
      if ( GetFullPathNameW(lpFileName, 0x104u, (LPWSTR)this + 16, (LPWSTR *)&pguid) )
      {
        FileDir = SAL2::GetFileDir(v9, v11, (_DWORD)this + 552, v12);
        *a8 = FileDir;
        if ( FileDir < 0 )
          return this;
        File = SAL2::CSALFileStore::InternalCreateFile(this);
      }
      else
      {
        File = GetLastError();
        if ( File > 0 )
          File = (unsigned __int16)File | 0x80070000;
      }
      *a8 = File;
      return this;
    }
    *((_QWORD *)this + 3) = a3;
    ((void (__fastcall *)(struct IStream *))a3->lpVtbl->AddRef)(a3);
    *(_WORD *)v9 = 0;
    *((_WORD *)this + 276) = 0;
    pguid = 0;
    v10 = CoCreateGuid(&pguid);
    *a8 = v10;
    if ( v10 >= 0 )
    {
      *((_DWORD *)this + 272) = pguid.Data1;
      *((_DWORD *)this + 273) = *(_DWORD *)&pguid.Data2;
      *((_DWORD *)this + 274) = *(_DWORD *)pguid.Data4;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180080678  mov     [rsp+arg_10], rbx
0x18008067d  mov     [rsp+arg_18], rsi
0x180080682  push    rdi
0x180080683  sub     rsp, 40h
0x180080687  mov     rax, cs:__security_cookie
0x18008068e  xor     rax, rsp
0x180080691  mov     [rsp+48h+var_18], rax
0x180080696  mov     rdi, [rsp+48h+arg_38]
0x18008069e  lea     rax, ??_7CSALFileStore@SAL2@@6B@; const SAL2::CSALFileStore::`vftable'
0x1800806a5  mov     [rcx], rax
0x1800806a8  mov     r10, rdx
0x1800806ab  mov     eax, [rsp+48h+arg_28]
0x1800806af  mov     rbx, rcx
0x1800806b2  mov     [rcx+434h], eax
0x1800806b8  mov     eax, [rsp+48h+arg_20]
0x1800806bc  mov     [rcx+438h], eax
0x1800806c2  mov     dword ptr [rcx+8], 0
0x1800806c9  mov     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x1800806d1  mov     qword ptr [rcx+18h], 0
0x1800806d9  mov     [rcx+430h], r9d
0x1800806e0  mov     dword ptr [rcx+43Ch], 60000000h
0x1800806ea  cmp     dword ptr [rdi], 0
0x1800806ed  jl      loc_1800807AA
0x1800806f3  lea     rsi, [rcx+20h]
0x1800806f7  test    r8, r8
0x1800806fa  jz      short loc_180080754
0x1800806fc  mov     [rcx+18h], r8
0x180080700  mov     rcx, r8
0x180080703  mov     rax, [r8]
0x180080706  mov     rax, [rax+8]
0x18008070a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008070f  xor     eax, eax
0x180080711  lea     rcx, [rsp+48h+pguid]; pguid
0x180080716  xorps   xmm0, xmm0
0x180080719  mov     [rsi], ax
0x18008071c  mov     [rbx+228h], ax
0x180080723  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x180080728  call    cs:__imp_CoCreateGuid
0x18008072e  mov     [rdi], eax
0x180080730  test    eax, eax
0x180080732  js      short loc_1800807AA
0x180080734  mov     eax, [rsp+48h+pguid.Data1]
0x180080738  mov     [rbx+440h], eax
0x18008073e  mov     eax, dword ptr [rsp+48h+pguid.Data2]
0x180080742  mov     [rbx+444h], eax
0x180080748  mov     eax, dword ptr [rsp+48h+pguid.Data4]
0x18008074c  mov     [rbx+448h], eax
0x180080752  jmp     short loc_1800807AA
0x180080754  lea     r9, [rsp+48h+pguid]; lpFilePart
0x180080759  mov     qword ptr [rsp+48h+pguid.Data1], 0
0x180080762  mov     r8, rsi; lpBuffer
0x180080765  mov     edx, 104h; nBufferLength
0x18008076a  mov     rcx, r10; lpFileName
0x18008076d  call    cs:__imp_GetFullPathNameW
0x180080773  test    eax, eax
0x180080775  jnz     short loc_18008078B
0x180080777  call    cs:__imp_GetLastError
0x18008077d  test    eax, eax
0x18008077f  jle     short loc_1800807A8
0x180080781  movzx   eax, ax
0x180080784  or      eax, 80070000h
0x180080789  jmp     short loc_1800807A8
0x18008078b  lea     r8, [rbx+228h]; unsigned int
0x180080792  mov     rcx, rsi; this
0x180080795  call    ?GetFileDir@SAL2@@YAJPEAGK0@Z; SAL2::GetFileDir(ushort *,ulong,ushort *)
0x18008079a  mov     [rdi], eax
0x18008079c  test    eax, eax
0x18008079e  js      short loc_1800807AA
0x1800807a0  mov     rcx, rbx; this
0x1800807a3  call    ?InternalCreateFile@CSALFileStore@SAL2@@IEAAJXZ; SAL2::CSALFileStore::InternalCreateFile(void)
0x1800807a8  mov     [rdi], eax
0x1800807aa  mov     rax, rbx
0x1800807ad  mov     rcx, [rsp+48h+var_18]
0x1800807b2  xor     rcx, rsp; StackCookie
0x1800807b5  call    __security_check_cookie
0x1800807ba  mov     rbx, [rsp+48h+arg_10]
0x1800807bf  mov     rsi, [rsp+48h+arg_18]
0x1800807c4  add     rsp, 40h
0x1800807c8  pop     rdi
0x1800807c9  retn
```
