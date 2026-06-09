# SBFThunk::Cv2ThunkFileWriter::InternalInitialize(bool)

- ea: `0x18004ae20`
- end: `0x18004aff8`
- name: `?InternalInitialize@Cv2ThunkFileWriter@SBFThunk@@AEAAJ_N@Z`
- size: `472`
- prototype: `__int64 __fastcall(SBFThunk::Cv2ThunkFileWriter *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045490`

## callees

- `0x180001c00`
- `0x18004849c`
- `0x18004ae20`
- `0x18004b0dc`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004ae98`
- `KERNEL32!LeaveCriticalSection` at `0x18004ae98`
- `KERNEL32!EnterCriticalSection` at `0x18004ae51`
- `KERNEL32!EnterCriticalSection` at `0x18004ae51`
- `ole32!CoCreateInstance` at `0x18004aee2`
- `ole32!CoCreateInstance` at `0x18004aee2`

## pseudocode

```c
__int64 __fastcall SBFThunk::Cv2ThunkFileWriter::InternalInitialize(
        SBFThunk::Cv2ThunkFileWriter *this,
        unsigned __int8 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int v3; // ebp
  bool v5; // zf
  HRESULT Instance; // ebx
  _QWORD *v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rdx
  int v11; // ecx
  unsigned int v12; // r9d
  __int64 v13; // r8
  __int64 v14; // [rsp+40h] [rbp-28h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 584);
  v3 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 584));
  v5 = *((_DWORD *)this + 156) == 0;
  v14 = 0;
  if ( !v5 )
  {
    Instance = -2147418113;
LABEL_3:
    SBFThunk::Cv2ThunkFileWriter::InternalUninitialize(this);
    goto LABEL_4;
  }
  v8 = (_QWORD *)((char *)this + 560);
  Instance = CoCreateInstance(&CLSID_SBFCore, 0, 3u, &IID_ISBFFile, (LPVOID *)this + 70);
  if ( Instance < 0 )
    goto LABEL_3;
  Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v8)(*v8, &IID_IStreamBufferInitialize, &v14);
  if ( Instance < 0 )
    goto LABEL_3;
  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v14 + 24LL))(
               v14,
               *(_QWORD *)(*((_QWORD *)this + 67) + 336LL));
  if ( Instance < 0 )
    goto LABEL_3;
  v9 = *((_QWORD *)this + 69);
  if ( v9 )
  {
    v10 = *(_QWORD *)(v9 + 16);
    v11 = *(_DWORD *)(v9 + 24);
    v12 = v11 - 1;
    if ( !v11 )
      v12 = 0;
    v13 = (v10 + 8) & -(__int64)(v10 != 0);
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 32LL))(v14, v12, v13);
  if ( Instance < 0 )
    goto LABEL_3;
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64, int, int))(*(_QWORD *)*v8 + 24LL))(
               *v8,
               *((_QWORD *)this + 144),
               (char *)this + 628,
               1,
               -1073741824,
               4 * v3 + 1);
  if ( Instance < 0 )
    goto LABEL_3;
  Instance = SBFThunk::Cv2ThunkFileWriter::CreateTimelineWriter(this);
  if ( Instance < 0 )
    goto LABEL_3;
  *((_DWORD *)this + 156) = 1;
LABEL_4:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  LeaveCriticalSection(v2);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18004ae20  mov     [rsp+arg_8], rbx
0x18004ae25  mov     [rsp+arg_10], rbp
0x18004ae2a  push    rsi
0x18004ae2b  push    rdi
0x18004ae2c  push    r14
0x18004ae2e  sub     rsp, 50h
0x18004ae32  mov     rax, cs:__security_cookie
0x18004ae39  xor     rax, rsp
0x18004ae3c  mov     [rsp+68h+var_20], rax
0x18004ae41  lea     rsi, [rcx+248h]
0x18004ae48  movzx   ebp, dl
0x18004ae4b  mov     rdi, rcx
0x18004ae4e  mov     rcx, rsi; lpCriticalSection
0x18004ae51  call    cs:__imp_EnterCriticalSection
0x18004ae57  cmp     dword ptr [rdi+270h], 0
0x18004ae5e  mov     [rsp+68h+var_28], 0
0x18004ae67  jz      short loc_18004AEC2
0x18004ae69  mov     ebx, 8000FFFFh
0x18004ae6e  mov     rcx, rdi; this
0x18004ae71  call    ?InternalUninitialize@Cv2ThunkFileWriter@SBFThunk@@AEAAXXZ; SBFThunk::Cv2ThunkFileWriter::InternalUninitialize(void)
0x18004ae76  mov     rcx, [rsp+68h+var_28]
0x18004ae7b  test    rcx, rcx
0x18004ae7e  jz      short loc_18004AE95
0x18004ae80  mov     rax, [rcx]
0x18004ae83  mov     rax, [rax+10h]
0x18004ae87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae8c  mov     [rsp+68h+var_28], 0
0x18004ae95  mov     rcx, rsi; lpCriticalSection
0x18004ae98  call    cs:__imp_LeaveCriticalSection
0x18004ae9e  mov     eax, ebx
0x18004aea0  mov     rcx, [rsp+68h+var_20]
0x18004aea5  xor     rcx, rsp; StackCookie
0x18004aea8  call    __security_check_cookie
0x18004aead  lea     r11, [rsp+68h+var_18]
0x18004aeb2  mov     rbx, [r11+28h]
0x18004aeb6  mov     rbp, [r11+30h]
0x18004aeba  mov     rsp, r11
0x18004aebd  pop     r14
0x18004aebf  pop     rdi
0x18004aec0  pop     rsi
0x18004aec1  retn
0x18004aec2  xor     edx, edx; pUnkOuter
0x18004aec4  lea     r14, [rdi+230h]
0x18004aecb  lea     r9, IID_ISBFFile; riid
0x18004aed2  mov     [rsp+68h+ppv], r14; ppv
0x18004aed7  lea     rcx, CLSID_SBFCore; rclsid
0x18004aede  lea     r8d, [rdx+3]; dwClsContext
0x18004aee2  call    cs:__imp_CoCreateInstance
0x18004aee8  mov     ebx, eax
0x18004aeea  test    eax, eax
0x18004aeec  js      short loc_18004AE6E
0x18004aeee  mov     rcx, [r14]
0x18004aef1  lea     r8, [rsp+68h+var_28]
0x18004aef6  lea     rdx, IID_IStreamBufferInitialize
0x18004aefd  mov     rax, [rcx]
0x18004af00  mov     rax, [rax]
0x18004af03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af08  mov     ebx, eax
0x18004af0a  test    eax, eax
0x18004af0c  js      loc_18004AE6E
0x18004af12  mov     rcx, [rsp+68h+var_28]
0x18004af17  mov     rdx, [rdi+218h]
0x18004af1e  mov     rax, [rcx]
0x18004af21  mov     rdx, [rdx+150h]
0x18004af28  mov     rax, [rax+18h]
0x18004af2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af31  mov     ebx, eax
0x18004af33  test    eax, eax
0x18004af35  js      loc_18004AE6E
0x18004af3b  mov     r10, [rsp+68h+var_28]
0x18004af40  mov     rcx, [rdi+228h]
0x18004af47  mov     rax, [r10]
0x18004af4a  mov     r11, [rax+20h]
0x18004af4e  test    rcx, rcx
0x18004af51  jz      short loc_18004AF75
0x18004af53  mov     rdx, [rcx+10h]
0x18004af57  xor     eax, eax
0x18004af59  mov     ecx, [rcx+18h]
0x18004af5c  test    ecx, ecx
0x18004af5e  lea     r9d, [rcx-1]
0x18004af62  cmovz   r9d, eax
0x18004af66  lea     rax, [rdx+8]
0x18004af6a  neg     rdx
0x18004af6d  sbb     r8, r8
0x18004af70  and     r8, rax
0x18004af73  jmp     short loc_18004AF7B
0x18004af75  xor     r9d, r9d
0x18004af78  xor     r8d, r8d
0x18004af7b  mov     edx, r9d
0x18004af7e  mov     rcx, r10
0x18004af81  mov     rax, r11
0x18004af84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af89  mov     ebx, eax
0x18004af8b  test    eax, eax
0x18004af8d  js      loc_18004AE6E
0x18004af93  mov     r11, [r14]
0x18004af96  lea     eax, ds:1[rbp*4]
0x18004af9d  mov     rdx, [rdi+480h]
0x18004afa4  lea     r8, [rdi+274h]
0x18004afab  mov     [rsp+68h+var_40], eax
0x18004afaf  mov     ebp, 1
0x18004afb4  mov     r9d, ebp
0x18004afb7  mov     dword ptr [rsp+68h+ppv], 0C0000000h
0x18004afbf  mov     rcx, [r11]
0x18004afc2  mov     r10, [rcx+18h]
0x18004afc6  mov     rcx, r11
0x18004afc9  mov     rax, r10
0x18004afcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afd1  mov     ebx, eax
0x18004afd3  test    eax, eax
0x18004afd5  js      loc_18004AE6E
0x18004afdb  mov     rcx, rdi; this
0x18004afde  call    ?CreateTimelineWriter@Cv2ThunkFileWriter@SBFThunk@@AEAAJXZ; SBFThunk::Cv2ThunkFileWriter::CreateTimelineWriter(void)
0x18004afe3  mov     ebx, eax
0x18004afe5  test    eax, eax
0x18004afe7  js      loc_18004AE6E
0x18004afed  mov     [rdi+270h], ebp
0x18004aff3  jmp     loc_18004AE76
```
