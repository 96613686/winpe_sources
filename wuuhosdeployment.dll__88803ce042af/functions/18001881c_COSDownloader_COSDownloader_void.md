# COSDownloader::~COSDownloader(void)

- ea: `0x18001881c`
- end: `0x180018b13`
- name: `??1COSDownloader@@UEAA@XZ`
- size: `759`
- prototype: `void __fastcall(COSDownloader *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800187e0`

## callees

- `0x180005f64`
- `0x18001881c`
- `0x180042a24`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018864`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001889c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018a50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018a7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018ae8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018af6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018864`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001889c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018a50`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018a7c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018ae8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018af6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018905`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018905`
- `OLEAUT32!__imp_SysFreeString` at `0x1800189d9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800189d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall COSDownloader::~COSDownloader(COSDownloader *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  const struct std::nothrow_t *v4; // rdx
  void *v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  __int64 v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx

  v2 = *((_QWORD *)this + 73);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 73) = 0;
  }
  *((_QWORD *)this + 67) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 544));
  v3 = *((_QWORD *)this + 66);
  *((_QWORD *)this + 66) = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 40LL))(v3, 1);
  *((_QWORD *)this + 60) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 488));
  v5 = (void *)*((_QWORD *)this + 56);
  if ( v5 )
  {
    operator delete(v5, v4);
    *((_QWORD *)this + 56) = 0;
  }
  v6 = *((_QWORD *)this + 54);
  if ( v6 )
  {
    (**(void (__fastcall ***)(__int64, __int64))(v6 + 8))(v6 + 8, 1);
    *((_QWORD *)this + 54) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 53);
  if ( v7 )
  {
    operator delete(v7, v4);
    *((_QWORD *)this + 53) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 51);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 51) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 50);
  if ( v9 )
  {
    operator delete(v9, v4);
    *((_QWORD *)this + 50) = 0;
  }
  v10 = (void *)*((_QWORD *)this + 48);
  if ( v10 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v10);
    *((_QWORD *)this + 48) = 0;
  }
  v11 = (void *)*((_QWORD *)this + 47);
  if ( v11 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v11);
    *((_QWORD *)this + 47) = 0;
  }
  v12 = (void *)*((_QWORD *)this + 46);
  if ( v12 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v12);
    *((_QWORD *)this + 46) = 0;
  }
  v13 = (void *)*((_QWORD *)this + 45);
  if ( v13 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v13);
    *((_QWORD *)this + 45) = 0;
  }
  v14 = (void *)*((_QWORD *)this + 44);
  if ( v14 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v14);
    *((_QWORD *)this + 44) = 0;
  }
  v15 = (void *)*((_QWORD *)this + 43);
  if ( v15 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v15);
    *((_QWORD *)this + 43) = 0;
  }
  v16 = (void *)*((_QWORD *)this + 41);
  if ( v16 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v16);
    *((_QWORD *)this + 41) = 0;
  }
  SysFreeString(*((BSTR *)this + 35));
  *((_QWORD *)this + 35) = 0;
  v17 = *((_QWORD *)this + 34);
  if ( v17 )
  {
    (**(void (__fastcall ***)(__int64, __int64))(v17 + 8))(v17 + 8, 1);
    *((_QWORD *)this + 34) = 0;
  }
  v18 = (void *)*((_QWORD *)this + 33);
  if ( v18 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v18);
    *((_QWORD *)this + 33) = 0;
  }
  v19 = (void *)*((_QWORD *)this + 32);
  if ( v19 )
  {
    operator delete(v19, (const struct std::nothrow_t *)0x38);
    *((_QWORD *)this + 32) = 0;
  }
  *((_QWORD *)this + 26) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v20 = (void *)*((_QWORD *)this + 25);
  if ( v20 )
  {
    CSusBaseAllocTag<942762101>::operator delete(v20);
    *((_QWORD *)this + 25) = 0;
  }
  *((_QWORD *)this + 19) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  v21 = *((_QWORD *)this + 18);
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    *((_QWORD *)this + 18) = 0;
  }
  v22 = *((_QWORD *)this + 17);
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    *((_QWORD *)this + 17) = 0;
  }
  v23 = *((_QWORD *)this + 16);
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    *((_QWORD *)this + 16) = 0;
  }
  *((_QWORD *)this + 10) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  *((_QWORD *)this + 3) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18001881c  mov     [rsp+arg_0], rbx
0x180018821  mov     [rsp+arg_8], rsi
0x180018826  push    rdi
0x180018827  sub     rsp, 20h
0x18001882b  mov     rbx, rcx
0x18001882e  mov     rcx, [rcx+248h]
0x180018835  xor     edi, edi
0x180018837  test    rcx, rcx
0x18001883a  jz      short loc_18001884F
0x18001883c  mov     rax, [rcx]
0x18001883f  mov     rax, [rax+10h]
0x180018843  call    _guard_dispatch_icall
0x180018848  mov     [rbx+248h], rdi
0x18001884f  lea     rsi, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180018856  mov     [rbx+218h], rsi
0x18001885d  lea     rcx, [rbx+220h]; lpCriticalSection
0x180018864  call    cs:__imp_DeleteCriticalSection
0x18001886a  mov     rcx, [rbx+210h]
0x180018871  mov     [rbx+210h], rdi
0x180018878  test    rcx, rcx
0x18001887b  jz      short loc_18001888E
0x18001887d  mov     rax, [rcx]
0x180018880  mov     edx, 1
0x180018885  mov     rax, [rax+28h]
0x180018889  call    _guard_dispatch_icall
0x18001888e  mov     [rbx+1E0h], rsi
0x180018895  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x18001889c  call    cs:__imp_DeleteCriticalSection
0x1800188a2  mov     rcx, [rbx+1C0h]; void *
0x1800188a9  test    rcx, rcx
0x1800188ac  jz      short loc_1800188BA
0x1800188ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800188b3  mov     [rbx+1C0h], rdi
0x1800188ba  mov     rcx, [rbx+1B0h]
0x1800188c1  test    rcx, rcx
0x1800188c4  jz      short loc_1800188E1
0x1800188c6  add     rcx, 8
0x1800188ca  mov     rax, [rcx]
0x1800188cd  mov     edx, 1
0x1800188d2  mov     rax, [rax]
0x1800188d5  call    _guard_dispatch_icall
0x1800188da  mov     [rbx+1B0h], rdi
0x1800188e1  mov     rcx, [rbx+1A8h]; void *
0x1800188e8  test    rcx, rcx
0x1800188eb  jz      short loc_1800188F9
0x1800188ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800188f2  mov     [rbx+1A8h], rdi
0x1800188f9  mov     rcx, [rbx+198h]; hObject
0x180018900  test    rcx, rcx
0x180018903  jz      short loc_180018912
0x180018905  call    cs:__imp_CloseHandle
0x18001890b  mov     [rbx+198h], rdi
0x180018912  mov     rcx, [rbx+190h]; void *
0x180018919  test    rcx, rcx
0x18001891c  jz      short loc_18001892A
0x18001891e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018923  mov     [rbx+190h], rdi
0x18001892a  mov     rcx, [rbx+180h]; lpMem
0x180018931  test    rcx, rcx
0x180018934  jz      short loc_180018942
0x180018936  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001893b  mov     [rbx+180h], rdi
0x180018942  mov     rcx, [rbx+178h]; lpMem
0x180018949  test    rcx, rcx
0x18001894c  jz      short loc_18001895A
0x18001894e  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180018953  mov     [rbx+178h], rdi
0x18001895a  mov     rcx, [rbx+170h]; lpMem
0x180018961  test    rcx, rcx
0x180018964  jz      short loc_180018972
0x180018966  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001896b  mov     [rbx+170h], rdi
0x180018972  mov     rcx, [rbx+168h]; lpMem
0x180018979  test    rcx, rcx
0x18001897c  jz      short loc_18001898A
0x18001897e  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180018983  mov     [rbx+168h], rdi
0x18001898a  mov     rcx, [rbx+160h]; lpMem
0x180018991  test    rcx, rcx
0x180018994  jz      short loc_1800189A2
0x180018996  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x18001899b  mov     [rbx+160h], rdi
0x1800189a2  mov     rcx, [rbx+158h]; lpMem
0x1800189a9  test    rcx, rcx
0x1800189ac  jz      short loc_1800189BA
0x1800189ae  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800189b3  mov     [rbx+158h], rdi
0x1800189ba  mov     rcx, [rbx+148h]; lpMem
0x1800189c1  test    rcx, rcx
0x1800189c4  jz      short loc_1800189D2
0x1800189c6  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x1800189cb  mov     [rbx+148h], rdi
0x1800189d2  mov     rcx, [rbx+118h]; bstrString
0x1800189d9  call    cs:__imp_SysFreeString
0x1800189df  mov     [rbx+118h], rdi
0x1800189e6  mov     rcx, [rbx+110h]
0x1800189ed  test    rcx, rcx
0x1800189f0  jz      short loc_180018A0D
0x1800189f2  add     rcx, 8
0x1800189f6  mov     rax, [rcx]
0x1800189f9  mov     edx, 1
0x1800189fe  mov     rax, [rax]
0x180018a01  call    _guard_dispatch_icall
0x180018a06  mov     [rbx+110h], rdi
0x180018a0d  mov     rcx, [rbx+108h]; lpMem
0x180018a14  test    rcx, rcx
0x180018a17  jz      short loc_180018A25
0x180018a19  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180018a1e  mov     [rbx+108h], rdi
0x180018a25  mov     rcx, [rbx+100h]; void *
0x180018a2c  test    rcx, rcx
0x180018a2f  jz      short loc_180018A42
0x180018a31  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x180018a36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180018a3b  mov     [rbx+100h], rdi
0x180018a42  mov     [rbx+0D0h], rsi
0x180018a49  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x180018a50  call    cs:__imp_DeleteCriticalSection
0x180018a56  mov     rcx, [rbx+0C8h]; lpMem
0x180018a5d  test    rcx, rcx
0x180018a60  jz      short loc_180018A6E
0x180018a62  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180018a67  mov     [rbx+0C8h], rdi
0x180018a6e  mov     [rbx+98h], rsi
0x180018a75  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180018a7c  call    cs:__imp_DeleteCriticalSection
0x180018a82  nop
0x180018a83  mov     rcx, [rbx+90h]
0x180018a8a  test    rcx, rcx
0x180018a8d  jz      short loc_180018AA2
0x180018a8f  mov     rax, [rcx]
0x180018a92  mov     rax, [rax+10h]
0x180018a96  call    _guard_dispatch_icall
0x180018a9b  mov     [rbx+90h], rdi
0x180018aa2  mov     rcx, [rbx+88h]
0x180018aa9  test    rcx, rcx
0x180018aac  jz      short loc_180018AC1
0x180018aae  mov     rax, [rcx]
0x180018ab1  mov     rax, [rax+10h]
0x180018ab5  call    _guard_dispatch_icall
0x180018aba  mov     [rbx+88h], rdi
0x180018ac1  mov     rcx, [rbx+80h]
0x180018ac8  test    rcx, rcx
0x180018acb  jz      short loc_180018AE0
0x180018acd  mov     rax, [rcx]
0x180018ad0  mov     rax, [rax+10h]
0x180018ad4  call    _guard_dispatch_icall
0x180018ad9  mov     [rbx+80h], rdi
0x180018ae0  mov     [rbx+50h], rsi
0x180018ae4  lea     rcx, [rbx+58h]; lpCriticalSection
0x180018ae8  call    cs:__imp_DeleteCriticalSection
0x180018aee  mov     [rbx+18h], rsi
0x180018af2  lea     rcx, [rbx+20h]; lpCriticalSection
0x180018af6  call    cs:__imp_DeleteCriticalSection
0x180018afc  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180018b03  mov     rbx, [rsp+28h+arg_0]
0x180018b08  mov     rsi, [rsp+28h+arg_8]
0x180018b0d  add     rsp, 20h
0x180018b11  pop     rdi
0x180018b12  retn
```
