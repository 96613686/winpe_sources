# CSchedule::GetTargetComputer(ushort * *)

- ea: `0x180029d50`
- end: `0x180029e77`
- name: `?GetTargetComputer@CSchedule@@UEAAJPEAPEAG@Z`
- size: `295`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040c0`
- `0x180029d50`
- `0x1800306c2`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029def`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029def`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180029ddf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180029ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e1e`

## pseudocode

```c
signed int __fastcall CSchedule::GetTargetComputer(CSchedule *this, unsigned __int16 **a2)
{
  signed int result; // eax
  const unsigned __int16 *v5; // rbx
  __int64 v6; // rax
  DWORD v7; // eax
  unsigned __int16 *v8; // rax
  int v9; // eax
  int v10; // ecx
  DWORD nSize[4]; // [rsp+20h] [rbp-238h] BYREF
  int v12; // [rsp+30h] [rbp-228h] BYREF
  WCHAR Buffer; // [rsp+34h] [rbp-224h] BYREF
  _BYTE v14[522]; // [rsp+36h] [rbp-222h] BYREF

  if ( !a2 )
    return -2147024809;
  v12 = *(_DWORD *)L"\\\\";
  Buffer = asc_180056B50[2];
  nSize[0] = 257;
  memset_0(v14, 0, 0x200u);
  v5 = (const unsigned __int16 *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    v7 = v6 + 1;
LABEL_11:
    nSize[0] = v7;
    v8 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v7);
    *a2 = v8;
    if ( !v8 )
      return -2147024882;
    v9 = StringCchCopyW(v8, nSize[0], v5);
    v10 = 0;
    if ( v9 < 0 )
      return v9;
    return v10;
  }
  if ( GetComputerNameW(&Buffer, nSize) )
  {
    v5 = (const unsigned __int16 *)&v12;
    v7 = nSize[0] + 3;
    goto LABEL_11;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180029d50  mov     [rsp+arg_10], rbx
0x180029d55  mov     [rsp+arg_18], rsi
0x180029d5a  push    rdi
0x180029d5b  sub     rsp, 250h
0x180029d62  mov     rax, cs:__security_cookie
0x180029d69  xor     rax, rsp
0x180029d6c  mov     [rsp+258h+var_18], rax
0x180029d74  xor     esi, esi
0x180029d76  mov     rdi, rdx
0x180029d79  mov     rbx, rcx
0x180029d7c  test    rdx, rdx
0x180029d7f  jnz     short loc_180029D8B
0x180029d81  mov     eax, 80070057h
0x180029d86  jmp     loc_180029E51
0x180029d8b  mov     eax, dword ptr cs:asc_180056B50; "\\\\"
0x180029d91  lea     rcx, [rsp+258h+var_222]; void *
0x180029d96  mov     [rsp+258h+var_228], eax
0x180029d9a  xor     edx, edx; Val
0x180029d9c  movzx   eax, word ptr cs:asc_180056B50+4; ""
0x180029da3  mov     r8d, 200h; Size
0x180029da9  mov     [rsp+258h+Buffer], ax
0x180029dae  mov     [rsp+258h+nSize], 101h
0x180029db6  call    memset_0
0x180029dbb  mov     rbx, [rbx+38h]
0x180029dbf  test    rbx, rbx
0x180029dc2  jz      short loc_180029DD5
0x180029dc4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029dc8  inc     rax
0x180029dcb  cmp     [rbx+rax*2], si
0x180029dcf  jnz     short loc_180029DC8
0x180029dd1  inc     eax
0x180029dd3  jmp     short loc_180029E15
0x180029dd5  lea     rdx, [rsp+258h+nSize]; nSize
0x180029dda  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x180029ddf  call    cs:__imp_GetComputerNameW
0x180029de6  nop     dword ptr [rax+rax+00h]
0x180029deb  test    eax, eax
0x180029ded  jnz     short loc_180029E09
0x180029def  call    cs:__imp_GetLastError
0x180029df6  nop     dword ptr [rax+rax+00h]
0x180029dfb  test    eax, eax
0x180029dfd  jle     short loc_180029E51
0x180029dff  movzx   eax, ax
0x180029e02  or      eax, 80070000h
0x180029e07  jmp     short loc_180029E51
0x180029e09  mov     eax, [rsp+258h+nSize]
0x180029e0d  lea     rbx, [rsp+258h+var_228]
0x180029e12  add     eax, 3
0x180029e15  mov     ecx, eax
0x180029e17  add     rcx, rcx; cb
0x180029e1a  mov     [rsp+258h+nSize], eax
0x180029e1e  call    cs:__imp_CoTaskMemAlloc
0x180029e25  nop     dword ptr [rax+rax+00h]
0x180029e2a  mov     [rdi], rax
0x180029e2d  test    rax, rax
0x180029e30  jnz     short loc_180029E39
0x180029e32  mov     eax, 8007000Eh
0x180029e37  jmp     short loc_180029E51
0x180029e39  mov     edx, [rsp+258h+nSize]; unsigned __int64
0x180029e3d  mov     r8, rbx; unsigned __int16 *
0x180029e40  mov     rcx, rax; unsigned __int16 *
0x180029e43  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029e48  test    eax, eax
0x180029e4a  mov     ecx, esi
0x180029e4c  cmovs   ecx, eax
0x180029e4f  mov     eax, ecx
0x180029e51  mov     rcx, [rsp+258h+var_18]
0x180029e59  xor     rcx, rsp; StackCookie
0x180029e5c  call    __security_check_cookie
0x180029e61  lea     r11, [rsp+258h+var_8]
0x180029e69  mov     rbx, [r11+20h]
0x180029e6d  mov     rsi, [r11+28h]
0x180029e71  mov     rsp, r11
0x180029e74  pop     rdi
0x180029e75  retn
```
