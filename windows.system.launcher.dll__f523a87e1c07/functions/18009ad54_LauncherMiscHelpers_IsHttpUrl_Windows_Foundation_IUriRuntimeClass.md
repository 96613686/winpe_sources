# LauncherMiscHelpers::IsHttpUrl(Windows::Foundation::IUriRuntimeClass *)

- ea: `0x18009ad54`
- end: `0x18009ae5e`
- name: `?IsHttpUrl@LauncherMiscHelpers@@YA_NPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `266`
- prototype: `bool __fastcall(LauncherMiscHelpers *__hidden this, struct Windows::Foundation::IUriRuntimeClass *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001fe90`
- `0x18007ec08`
- `0x180093998`

## callees

- `0x18009ad54`
- `0x180111010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ae06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ae27`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ae06`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ae27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009adf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ae17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009adf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009ae17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ad84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009adcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ae39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ae45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ad84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009adcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ae39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ae45`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall LauncherMiscHelpers::IsHttpUrl(
        LauncherMiscHelpers *this,
        struct Windows::Foundation::IUriRuntimeClass *a2)
{
  char v3; // di
  unsigned int (__fastcall *v4)(LauncherMiscHelpers *, HSTRING *); // rbx
  int (__fastcall *v5)(LauncherMiscHelpers *, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  PCWSTR v7; // rax
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF
  HSTRING v10; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v10 = 0;
  if ( this )
  {
    v4 = *(unsigned int (__fastcall **)(LauncherMiscHelpers *, HSTRING *))(*(_QWORD *)this + 48LL);
    WindowsDeleteString(0);
    v10 = 0;
    if ( !v4(this, &v10) )
    {
      if ( v10 )
      {
        string = 0;
        v5 = *(int (__fastcall **)(LauncherMiscHelpers *, HSTRING *))(*(_QWORD *)this + 136LL);
        WindowsDeleteString(0);
        string = 0;
        if ( v5(this, &string) >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( !(unsigned int)_o__wcsicmp(L"HTTP", StringRawBuffer)
            || (v7 = WindowsGetStringRawBuffer(string, 0), !(unsigned int)_o__wcsicmp(L"HTTPS", v7)) )
          {
            v3 = 1;
          }
        }
        WindowsDeleteString(string);
      }
    }
  }
  WindowsDeleteString(v10);
  return v3;
}

```

## disassembly

```asm
0x18009ad54  mov     [rsp+arg_10], rbx
0x18009ad59  mov     [rsp+arg_18], rsi
0x18009ad5e  push    rdi
0x18009ad5f  sub     rsp, 20h
0x18009ad63  mov     rsi, rcx
0x18009ad66  xor     dil, dil
0x18009ad69  mov     [rsp+28h+arg_8], 0
0x18009ad72  test    rcx, rcx
0x18009ad75  jz      loc_18009AE40
0x18009ad7b  mov     rax, [rcx]
0x18009ad7e  mov     rbx, [rax+30h]
0x18009ad82  xor     ecx, ecx; string
0x18009ad84  call    cs:__imp_WindowsDeleteString
0x18009ad8a  mov     [rsp+28h+arg_8], 0
0x18009ad93  lea     rdx, [rsp+28h+arg_8]
0x18009ad98  mov     rcx, rsi
0x18009ad9b  mov     rax, rbx
0x18009ad9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ada3  test    eax, eax
0x18009ada5  jnz     loc_18009AE40
0x18009adab  cmp     [rsp+28h+arg_8], 0
0x18009adb1  jz      loc_18009AE40
0x18009adb7  mov     [rsp+28h+string], 0
0x18009adc0  mov     rax, [rsi]
0x18009adc3  mov     rbx, [rax+88h]
0x18009adca  xor     ecx, ecx; string
0x18009adcc  call    cs:__imp_WindowsDeleteString
0x18009add2  mov     [rsp+28h+string], 0
0x18009addb  lea     rdx, [rsp+28h+string]
0x18009ade0  mov     rcx, rsi
0x18009ade3  mov     rax, rbx
0x18009ade6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adeb  test    eax, eax
0x18009aded  js      short loc_18009AE34
0x18009adef  xor     edx, edx; length
0x18009adf1  mov     rcx, [rsp+28h+string]; string
0x18009adf6  call    cs:__imp_WindowsGetStringRawBuffer
0x18009adfc  mov     rdx, rax
0x18009adff  lea     rcx, aHttp; "HTTP"
0x18009ae06  call    cs:__imp__o__wcsicmp
0x18009ae0c  test    eax, eax
0x18009ae0e  jz      short loc_18009AE31
0x18009ae10  xor     edx, edx; length
0x18009ae12  mov     rcx, [rsp+28h+string]; string
0x18009ae17  call    cs:__imp_WindowsGetStringRawBuffer
0x18009ae1d  mov     rdx, rax
0x18009ae20  lea     rcx, aHttps; "HTTPS"
0x18009ae27  call    cs:__imp__o__wcsicmp
0x18009ae2d  test    eax, eax
0x18009ae2f  jnz     short loc_18009AE34
0x18009ae31  mov     dil, 1
0x18009ae34  mov     rcx, [rsp+28h+string]; string
0x18009ae39  call    cs:__imp_WindowsDeleteString
0x18009ae3f  nop
0x18009ae40  mov     rcx, [rsp+28h+arg_8]; string
0x18009ae45  call    cs:__imp_WindowsDeleteString
0x18009ae4b  mov     al, dil
0x18009ae4e  mov     rbx, [rsp+28h+arg_10]
0x18009ae53  mov     rsi, [rsp+28h+arg_18]
0x18009ae58  add     rsp, 20h
0x18009ae5c  pop     rdi
0x18009ae5d  retn
```
