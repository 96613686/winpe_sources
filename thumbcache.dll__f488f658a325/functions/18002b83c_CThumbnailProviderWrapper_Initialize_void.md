# CThumbnailProviderWrapper::Initialize(void)

- ea: `0x18002b83c`
- end: `0x18002b957`
- name: `?Initialize@CThumbnailProviderWrapper@@QEAAJXZ`
- size: `283`
- prototype: `__int64 __fastcall(CThumbnailProviderWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800189b0`

## callees

- `0x18002a288`
- `0x18002b83c`
- `0x180035830`
- `0x180045cbc`
- `0x180047a40`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b889`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b889`

## string_xrefs

- `0x18002b92f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\ThumbnailCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CThumbnailProviderWrapper::Initialize(CThumbnailProviderWrapper *this)
{
  int started; // ebx
  void (*v4)(void *); // r8
  unsigned int v5; // edx
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF

  if ( !g_fEnableTimeout )
    goto LABEL_2;
  if ( !memcmp_0(&g_clsidActive, &GUID_NULL, 0x10u) )
    return (unsigned int)-2147175934;
  LODWORD(ppv) = 0;
  if ( (int)SHRegGetDWORD(
              HKEY_CURRENT_USER,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\ThumbnailCache",
              L"ExtractionTimeoutInMS",
              (unsigned int *)&ppv) >= 0 )
  {
    v5 = (unsigned int)ppv;
  }
  else
  {
    v5 = 60000;
    LODWORD(ppv) = 60000;
  }
  started = CSurrogateTimeout::StartTimer((struct _TP_TIMER **)this + 10, v5, v4);
  if ( started >= 0 )
  {
LABEL_2:
    ppv = 0;
    started = CoCreateInstance((const IID *const)this + 4, 0, 1u, &GUID_e357fccd_a995_4576_b01f_234630154e96, &ppv);
    if ( started >= 0 )
      started = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(
                  ppv,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  (char *)this + 48);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18002b83c  mov     [rsp+arg_8], rbx
0x18002b841  push    rdi
0x18002b842  sub     rsp, 40h
0x18002b846  mov     rax, cs:__security_cookie
0x18002b84d  xor     rax, rsp
0x18002b850  mov     [rsp+48h+var_10], rax
0x18002b855  mov     rdi, rcx
0x18002b858  cmp     cs:?g_fEnableTimeout@@3_NA, 0; bool g_fEnableTimeout
0x18002b85f  jnz     loc_18002B8F7
0x18002b865  mov     [rsp+48h+var_18], 0
0x18002b86e  lea     rcx, [rdi+40h]; rclsid
0x18002b872  lea     rax, [rsp+48h+var_18]
0x18002b877  mov     [rsp+48h+ppv], rax; ppv
0x18002b87c  lea     r9, _GUID_e357fccd_a995_4576_b01f_234630154e96; riid
0x18002b883  xor     edx, edx; pUnkOuter
0x18002b885  lea     r8d, [rdx+1]; dwClsContext
0x18002b889  call    cs:__imp_CoCreateInstance
0x18002b88f  mov     ebx, eax
0x18002b891  test    eax, eax
0x18002b893  js      short loc_18002B8B2
0x18002b895  mov     rcx, [rsp+48h+var_18]
0x18002b89a  mov     rax, [rcx]
0x18002b89d  lea     r8, [rdi+30h]
0x18002b8a1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002b8a8  mov     rax, [rax]
0x18002b8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8b0  mov     ebx, eax
0x18002b8b2  mov     rcx, [rsp+48h+var_18]
0x18002b8b7  test    rcx, rcx
0x18002b8ba  jz      short loc_18002B8C9
0x18002b8bc  mov     rax, [rcx]
0x18002b8bf  mov     rax, [rax+10h]
0x18002b8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8c8  nop
0x18002b8c9  mov     eax, ebx
0x18002b8cb  mov     rcx, [rsp+48h+var_10]
0x18002b8d0  xor     rcx, rsp; StackCookie
0x18002b8d3  call    __security_check_cookie
0x18002b8d8  mov     rbx, [rsp+48h+arg_8]
0x18002b8dd  add     rsp, 40h
0x18002b8e1  pop     rdi
0x18002b8e2  retn
0x18002b8e3  lea     rcx, [rdi+50h]; pv
0x18002b8e7  call    ?StartTimer@CSurrogateTimeout@@QEAAJIP6AXPEAX@Z@Z; CSurrogateTimeout::StartTimer(uint,void (*)(void *))
0x18002b8ec  mov     ebx, eax
0x18002b8ee  test    eax, eax
0x18002b8f0  js      short loc_18002B8C9
0x18002b8f2  jmp     loc_18002B865
0x18002b8f7  mov     r8d, 10h; Size
0x18002b8fd  lea     rdx, GUID_NULL; Buf2
0x18002b904  lea     rcx, ?g_clsidActive@@3U_GUID@@A; Buf1
0x18002b90b  call    memcmp_0
0x18002b910  test    eax, eax
0x18002b912  jnz     short loc_18002B91B
0x18002b914  mov     ebx, 8004B202h
0x18002b919  jmp     short loc_18002B8C9
0x18002b91b  mov     dword ptr [rsp+48h+var_18], 0
0x18002b923  lea     r9, [rsp+48h+var_18]; unsigned int *
0x18002b928  lea     r8, aExtractiontime; "ExtractionTimeoutInMS"
0x18002b92f  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002b936  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18002b93d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002b942  test    eax, eax
0x18002b944  jns     short loc_18002B951
0x18002b946  mov     edx, 0EA60h; unsigned int
0x18002b94b  mov     dword ptr [rsp+48h+var_18], edx
0x18002b94f  jmp     short loc_18002B8E3
0x18002b951  mov     edx, dword ptr [rsp+48h+var_18]
0x18002b955  jmp     short loc_18002B8E3
```
