# etw_recorder::init(etw_recorder::session const &)

- ea: `0x18005b208`
- end: `0x18005b62a`
- name: `?init@etw_recorder@@QEAAXAEBUsession@1@@Z`
- size: `1058`
- prototype: `void __fastcall(etw_recorder *__hidden this, const struct etw_recorder::session *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18004ec90`

## callees

- `0x180004510`
- `0x1800054e4`
- `0x1800054fc`
- `0x180005520`
- `0x18003af08`
- `0x180041564`
- `0x1800416a0`
- `0x180041e4c`
- `0x18004a1b4`
- `0x1800511ac`
- `0x18005b208`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18005b4b5`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18005b4d7`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18005b4b5`
- `api-ms-win-eventing-controller-l1-1-0!TraceSetInformation` at `0x18005b4d7`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18005b46a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18005b46a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005b319`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18005b319`

## string_xrefs

- `0x18005b553`: `etw log path (%zu)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall etw_recorder::init(etw_recorder *this, const struct etw_recorder::session *a2)
{
  char *v4; // rdx
  __int64 v5; // rax
  const CHAR *v6; // rdx
  __int64 v7; // rax
  const WCHAR *v8; // rsi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // r14
  __int64 *v11; // r12
  __int64 v12; // r13
  size_t v13; // r15
  _DWORD *v14; // rax
  HRESULT Guid; // eax
  const WCHAR *v16; // rdx
  etw_recorder *v17; // rdx
  int v18; // ecx
  size_t v19; // r15
  __int64 v20; // rcx
  ULONG started; // eax
  ULONG v22; // eax
  TRACEHANDLE v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  char TraceInformation[8]; // [rsp+30h] [rbp-D0h] BYREF
  char *v27[5]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = (char *)a2 + 40;
  if ( *((_QWORD *)v4 + 3) > 0xFu )
    v4 = *(char **)v4;
  v5 = windiag::char_to_wstring((__int64)v27, v4);
  std::wstring::operator=(this, v5);
  std::wstring::~wstring(v27);
  if ( *((_QWORD *)a2 + 3) <= 0xFu )
    v6 = (const CHAR *)a2;
  else
    v6 = *(const CHAR **)a2;
  v7 = windiag::char_to_wstring((__int64)v27, v6);
  v8 = (const WCHAR *)((char *)this + 32);
  std::wstring::operator=((char *)this + 32, v7);
  std::wstring::~wstring(v27);
  v9 = *((_QWORD *)this + 2);
  if ( v9 > 0x400 )
  {
    v24 = std::wstring::size(this);
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      111,
      0,
      "etw log path (%zu)",
      v24);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v10 = *((_QWORD *)this + 6);
  if ( v10 > 0x400 )
  {
    v25 = std::wstring::size((char *)this + 32);
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      111,
      0,
      "etw session name (%zu)",
      v25);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v11 = (__int64 *)((char *)this + 64);
  v12 = *((_BYTE *)a2 + 140) != 0 ? 0x28 : 0;
  v13 = v12 + 2 * v9 + 122 + 2 * (v10 + 1);
  std::vector<unsigned char>::resize((char *)this + 64);
  memset_0(*((void **)this + 8), 0, v13);
  v14 = (_DWORD *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 11) = v14;
  *v14 = v13;
  *(_DWORD *)(*((_QWORD *)this + 11) + 44LL) = 0x20000;
  Guid = CoCreateGuid((GUID *)(*((_QWORD *)this + 11) + 24LL));
  if ( Guid < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      Guid,
      0,
      "[%s:%d] failed; ",
      "init",
      211);
    throw (windiag::system_exception *)pExceptionObject;
  }
  *(_DWORD *)(*((_QWORD *)this + 11) + 64LL) = *((_DWORD *)a2 + 8);
  *(_DWORD *)(*((_QWORD *)this + 11) + 60LL) = *((_DWORD *)a2 + 18);
  *(_DWORD *)(*((_QWORD *)this + 11) + 116LL) = 120;
  *(_DWORD *)(*((_QWORD *)this + 11) + 112LL) = *(_DWORD *)(*((_QWORD *)this + 11) + 116LL) + 2 * (v10 + 1);
  if ( *((_BYTE *)a2 + 80) )
    *(_DWORD *)(*((_QWORD *)this + 11) + 52LL) = *((_DWORD *)a2 + 19);
  if ( *((_BYTE *)a2 + 88) )
    *(_DWORD *)(*((_QWORD *)this + 11) + 56LL) = *((_DWORD *)a2 + 21);
  if ( *((_BYTE *)a2 + 96) )
    *(_DWORD *)(*((_QWORD *)this + 11) + 48LL) = *((_DWORD *)a2 + 23);
  if ( *((_BYTE *)a2 + 104) )
    *(_DWORD *)(*((_QWORD *)this + 11) + 68LL) = *((_DWORD *)a2 + 25);
  if ( *((_QWORD *)this + 7) <= 7u )
    v16 = (const WCHAR *)((char *)this + 32);
  else
    v16 = *(const WCHAR **)v8;
  memcpy_0((void *)(*v11 + *(unsigned int *)(*((_QWORD *)this + 11) + 116LL)), v16, 2LL * *((_QWORD *)this + 6));
  if ( *((_QWORD *)this + 3) <= 7u )
    v17 = this;
  else
    v17 = *(etw_recorder **)this;
  memcpy_0((void *)(*v11 + *(unsigned int *)(*((_QWORD *)this + 11) + 112LL)), v17, 2LL * *((_QWORD *)this + 2));
  if ( *((_BYTE *)a2 + 140) )
  {
    v18 = v13;
    v19 = v13 - v12;
    *(_DWORD *)(*((_QWORD *)this + 11) + 72LL) = (v18 - v12) | 0x80FF0000;
    v20 = *v11;
    *(_DWORD *)(v19 + v20) = 1;
    *(_DWORD *)(v19 + v20 + 4) = 65545;
    *(_WORD *)(v19 + v20) += 9;
    ++*(_WORD *)(v19 + v20 + 2);
    *(_OWORD *)(v19 + v20 + 8) = *(_OWORD *)((char *)a2 + 108);
    *(_OWORD *)(v19 + v20 + 24) = *(_OWORD *)((char *)a2 + 124);
  }
  else if ( *((_BYTE *)a2 + 180) )
  {
    *(_DWORD *)(*((_QWORD *)this + 11) + 72LL) = *((_DWORD *)a2 + 44);
  }
  if ( *((_QWORD *)this + 7) > 7u )
    v8 = *(const WCHAR **)v8;
  started = StartTraceW((PTRACEHANDLE)this + 12, v8, *((PEVENT_TRACE_PROPERTIES *)this + 11));
  if ( started )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      started,
      0,
      "[%s:%d] failed; ",
      "init",
      259);
    throw (windiag::system_exception *)pExceptionObject;
  }
  if ( *((_BYTE *)a2 + 168) )
  {
    v22 = TraceSetInformation(
            *((_QWORD *)this + 12),
            TraceStackTracingInfo,
            *((PVOID *)a2 + 18),
            8 * ((__int64)(*((_QWORD *)a2 + 19) - *((_QWORD *)a2 + 18)) >> 3));
    if ( v22 )
    {
      windiag::system_exception::system_exception(
        (windiag::system_exception *)pExceptionObject,
        v22,
        0,
        "[%s:%d] failed; ",
        "init",
        266);
      throw (windiag::system_exception *)pExceptionObject;
    }
  }
  v23 = *((_QWORD *)this + 12);
  TraceInformation[0] = 1;
  TraceSetInformation(v23, TraceProviderBinaryTracking, TraceInformation, 1u);
}

```

## disassembly

```asm
0x18005b208  mov     [rsp-8+arg_10], rbx
0x18005b20d  push    rbp
0x18005b20e  push    rsi
0x18005b20f  push    rdi
0x18005b210  push    r12
0x18005b212  push    r13
0x18005b214  push    r14
0x18005b216  push    r15
0x18005b218  lea     rbp, [rsp-3A0h]
0x18005b220  sub     rsp, 4A0h
0x18005b227  mov     rax, cs:__security_cookie
0x18005b22e  xor     rax, rsp
0x18005b231  mov     [rbp+3D0h+var_40], rax
0x18005b238  mov     rdi, rdx
0x18005b23b  mov     rbx, rcx
0x18005b23e  add     rdx, 28h ; '('
0x18005b242  cmp     qword ptr [rdx+18h], 0Fh
0x18005b247  jbe     short loc_18005B24C
0x18005b249  mov     rdx, [rdx]
0x18005b24c  lea     rcx, [rsp+4D0h+var_498]
0x18005b251  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18005b256  mov     rdx, rax
0x18005b259  mov     rcx, rbx
0x18005b25c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005b261  lea     rcx, [rsp+4D0h+var_498]
0x18005b266  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b26b  cmp     qword ptr [rdi+18h], 0Fh
0x18005b270  jbe     short loc_18005B277
0x18005b272  mov     rdx, [rdi]
0x18005b275  jmp     short loc_18005B27A
0x18005b277  mov     rdx, rdi
0x18005b27a  lea     rcx, [rsp+4D0h+var_498]
0x18005b27f  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18005b284  lea     rsi, [rbx+20h]
0x18005b288  mov     rdx, rax
0x18005b28b  mov     rcx, rsi
0x18005b28e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005b293  lea     rcx, [rsp+4D0h+var_498]
0x18005b298  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005b29d  mov     rcx, [rbx+10h]
0x18005b2a1  mov     eax, 400h
0x18005b2a6  cmp     rcx, rax
0x18005b2a9  ja      loc_18005B543
0x18005b2af  mov     r14, [rbx+30h]
0x18005b2b3  cmp     r14, rax
0x18005b2b6  ja      loc_18005B57A
0x18005b2bc  mov     al, [rdi+8Ch]
0x18005b2c2  lea     r15, [r14+1]
0x18005b2c6  neg     al
0x18005b2c8  lea     r12, [rbx+40h]
0x18005b2cc  lea     rax, ds:7Ah[rcx*2]
0x18005b2d4  mov     rcx, r12
0x18005b2d7  sbb     r13, r13
0x18005b2da  and     r13d, 28h
0x18005b2de  add     rax, r13
0x18005b2e1  lea     r15, [rax+r15*2]
0x18005b2e5  mov     rdx, r15
0x18005b2e8  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18005b2ed  mov     rcx, [r12]; void *
0x18005b2f1  mov     r8, r15; Size
0x18005b2f4  xor     edx, edx; Val
0x18005b2f6  call    memset_0
0x18005b2fb  mov     rax, [r12]
0x18005b2ff  mov     [rbx+58h], rax
0x18005b303  mov     [rax], r15d
0x18005b306  mov     rax, [rbx+58h]
0x18005b30a  mov     dword ptr [rax+2Ch], 20000h
0x18005b311  mov     rcx, [rbx+58h]
0x18005b315  add     rcx, 18h; pguid
0x18005b319  call    cs:__imp_CoCreateGuid
0x18005b31f  test    eax, eax
0x18005b321  js      loc_18005B5B1
0x18005b327  mov     eax, [rdi+20h]
0x18005b32a  mov     rcx, [rbx+58h]
0x18005b32e  mov     [rcx+40h], eax
0x18005b331  mov     rcx, [rbx+58h]
0x18005b335  mov     eax, [rdi+48h]
0x18005b338  mov     [rcx+3Ch], eax
0x18005b33b  lea     rcx, [r14+1]
0x18005b33f  mov     rax, [rbx+58h]
0x18005b343  xor     r14d, r14d
0x18005b346  mov     dword ptr [rax+74h], 78h ; 'x'
0x18005b34d  mov     rdx, [rbx+58h]
0x18005b351  mov     eax, [rdx+74h]
0x18005b354  lea     ecx, [rax+rcx*2]
0x18005b357  mov     [rdx+70h], ecx
0x18005b35a  cmp     [rdi+50h], r14b
0x18005b35e  jz      short loc_18005B36A
0x18005b360  mov     rcx, [rbx+58h]
0x18005b364  mov     eax, [rdi+4Ch]
0x18005b367  mov     [rcx+34h], eax
0x18005b36a  cmp     [rdi+58h], r14b
0x18005b36e  jz      short loc_18005B37A
0x18005b370  mov     rcx, [rbx+58h]
0x18005b374  mov     eax, [rdi+54h]
0x18005b377  mov     [rcx+38h], eax
0x18005b37a  cmp     [rdi+60h], r14b
0x18005b37e  jz      short loc_18005B38A
0x18005b380  mov     rcx, [rbx+58h]
0x18005b384  mov     eax, [rdi+5Ch]
0x18005b387  mov     [rcx+30h], eax
0x18005b38a  cmp     [rdi+68h], r14b
0x18005b38e  jz      short loc_18005B39A
0x18005b390  mov     rcx, [rbx+58h]
0x18005b394  mov     eax, [rdi+64h]
0x18005b397  mov     [rcx+44h], eax
0x18005b39a  cmp     qword ptr [rsi+18h], 7
0x18005b39f  jbe     short loc_18005B3A6
0x18005b3a1  mov     rdx, [rsi]
0x18005b3a4  jmp     short loc_18005B3A9
0x18005b3a6  mov     rdx, rsi; Src
0x18005b3a9  mov     rax, [rbx+58h]
0x18005b3ad  mov     r8, [rbx+30h]
0x18005b3b1  add     r8, r8; Size
0x18005b3b4  mov     ecx, [rax+74h]
0x18005b3b7  add     rcx, [r12]; void *
0x18005b3bb  call    memcpy_0
0x18005b3c0  cmp     qword ptr [rbx+18h], 7
0x18005b3c5  jbe     short loc_18005B3CC
0x18005b3c7  mov     rdx, [rbx]
0x18005b3ca  jmp     short loc_18005B3CF
0x18005b3cc  mov     rdx, rbx; Src
0x18005b3cf  mov     rax, [rbx+58h]
0x18005b3d3  mov     r8, [rbx+10h]
0x18005b3d7  add     r8, r8; Size
0x18005b3da  mov     ecx, [rax+70h]
0x18005b3dd  add     rcx, [r12]; void *
0x18005b3e1  call    memcpy_0
0x18005b3e6  mov     edx, 1
0x18005b3eb  cmp     [rdi+8Ch], r14b
0x18005b3f2  jz      short loc_18005B43F
0x18005b3f4  mov     rax, [rbx+58h]
0x18005b3f8  mov     ecx, r15d
0x18005b3fb  sub     r15, r13
0x18005b3fe  sub     ecx, r13d
0x18005b401  or      ecx, 80FF0000h
0x18005b407  mov     [rax+48h], ecx
0x18005b40a  lea     eax, [rdx+8]
0x18005b40d  mov     rcx, [r12]
0x18005b411  mov     [r15+rcx], edx
0x18005b415  mov     dword ptr [r15+rcx+4], 10009h
0x18005b41e  add     [r15+rcx], ax
0x18005b423  add     [r15+rcx+2], dx
0x18005b429  movups  xmm0, xmmword ptr [rdi+6Ch]
0x18005b42d  movups  xmmword ptr [r15+rcx+8], xmm0
0x18005b433  movups  xmm1, xmmword ptr [rdi+7Ch]
0x18005b437  movups  xmmword ptr [r15+rcx+18h], xmm1
0x18005b43d  jmp     short loc_18005B455
0x18005b43f  cmp     [rdi+0B4h], r14b
0x18005b446  jz      short loc_18005B455
0x18005b448  mov     rcx, [rbx+58h]
0x18005b44c  mov     eax, [rdi+0B0h]
0x18005b452  mov     [rcx+48h], eax
0x18005b455  cmp     qword ptr [rsi+18h], 7
0x18005b45a  mov     r8, [rbx+58h]; Properties
0x18005b45e  jbe     short loc_18005B463
0x18005b460  mov     rsi, [rsi]
0x18005b463  mov     rdx, rsi; InstanceName
0x18005b466  lea     rcx, [rbx+60h]; TraceHandle
0x18005b46a  call    cs:__imp_StartTraceW
0x18005b470  test    eax, eax
0x18005b472  jnz     loc_18005B5EE
0x18005b478  cmp     [rdi+0A8h], r14b
0x18005b47f  jz      short loc_18005B4BF
0x18005b481  mov     r8, [rdi+90h]; TraceInformation
0x18005b488  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18005b492  mov     rax, [rdi+98h]
0x18005b499  mov     edx, 3; InformationClass
0x18005b49e  sub     rax, r8
0x18005b4a1  sar     rax, 3
0x18005b4a5  imul    rax, rcx
0x18005b4a9  mov     rcx, [rbx+60h]; SessionHandle
0x18005b4ad  lea     r9d, [rax+rax*2]
0x18005b4b1  shl     r9d, 3; InformationLength
0x18005b4b5  call    cs:__imp_TraceSetInformation
0x18005b4bb  test    eax, eax
0x18005b4bd  jnz     short loc_18005B507
0x18005b4bf  mov     rcx, [rbx+60h]; SessionHandle
0x18005b4c3  lea     r8, [rsp+4D0h+TraceInformation]; TraceInformation
0x18005b4c8  mov     r9d, 1; InformationLength
0x18005b4ce  mov     [rsp+4D0h+TraceInformation], 1
0x18005b4d3  lea     edx, [r9+11h]; InformationClass
0x18005b4d7  call    cs:__imp_TraceSetInformation
0x18005b4dd  mov     rcx, [rbp+3D0h+var_40]
0x18005b4e4  xor     rcx, rsp; StackCookie
0x18005b4e7  call    __security_check_cookie
0x18005b4ec  mov     rbx, [rsp+4D0h+arg_10]
0x18005b4f4  add     rsp, 4A0h
0x18005b4fb  pop     r15
0x18005b4fd  pop     r14
0x18005b4ff  pop     r13
0x18005b501  pop     r12
0x18005b503  pop     rdi
0x18005b504  pop     rsi
0x18005b505  pop     rbp
0x18005b506  retn
0x18005b507  mov     edx, eax; __int64
0x18005b509  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b510  lea     rax, aInit; "init"
0x18005b517  mov     [rsp+4D0h+var_4A8], 10Ah
0x18005b51f  xor     r8d, r8d; void *
0x18005b522  mov     [rsp+4D0h+var_4B0], rax
0x18005b527  lea     rcx, [rsp+4D0h+pExceptionObject]; this
0x18005b52c  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b531  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b538  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18005b53d  call    _CxxThrowException_0
0x18005b543  mov     rcx, rbx
0x18005b546  call    ?size@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KXZ; std::wstring::size(void)
0x18005b54b  xor     r8d, r8d; void *
0x18005b54e  mov     [rsp+4D0h+var_4B0], rax
0x18005b553  lea     r9, aEtwLogPathZu; "etw log path (%zu)"
0x18005b55a  lea     rcx, [rsp+4D0h+pExceptionObject]; this
0x18005b55f  lea     edx, [r8+6Fh]; __int64
0x18005b563  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b568  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b56f  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18005b574  call    _CxxThrowException_0
0x18005b57a  mov     rcx, rsi
0x18005b57d  call    ?size@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KXZ; std::wstring::size(void)
0x18005b582  xor     r8d, r8d; void *
0x18005b585  mov     [rsp+4D0h+var_4B0], rax
0x18005b58a  lea     r9, aEtwSessionName; "etw session name (%zu)"
0x18005b591  lea     rcx, [rsp+4D0h+pExceptionObject]; this
0x18005b596  lea     edx, [r8+6Fh]; __int64
0x18005b59a  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b59f  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b5a6  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18005b5ab  call    _CxxThrowException_0
0x18005b5b1  movsxd  rdx, eax; __int64
0x18005b5b4  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b5bb  lea     rax, aInit; "init"
0x18005b5c2  mov     [rsp+4D0h+var_4A8], 0D3h
0x18005b5ca  xor     r8d, r8d; void *
0x18005b5cd  mov     [rsp+4D0h+var_4B0], rax
0x18005b5d2  lea     rcx, [rsp+4D0h+pExceptionObject]; this
0x18005b5d7  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b5dc  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b5e3  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18005b5e8  call    _CxxThrowException_0
0x18005b5ee  mov     edx, eax; __int64
0x18005b5f0  lea     r9, aSDFailed; "[%s:%d] failed; "
0x18005b5f7  lea     rax, aInit; "init"
0x18005b5fe  mov     [rsp+4D0h+var_4A8], 103h
0x18005b606  xor     r8d, r8d; void *
0x18005b609  mov     [rsp+4D0h+var_4B0], rax
0x18005b60e  lea     rcx, [rsp+4D0h+pExceptionObject]; this
0x18005b613  call    ??0system_exception@windiag@@QEAA@_JPEBXPEBDZZ; windiag::system_exception::system_exception(__int64,void const *,char const *,...)
0x18005b618  lea     rdx, _TI2?AUsystem_exception@windiag@@; pThrowInfo
0x18005b61f  lea     rcx, [rsp+4D0h+pExceptionObject]; pExceptionObject
0x18005b624  call    _CxxThrowException_0
```
