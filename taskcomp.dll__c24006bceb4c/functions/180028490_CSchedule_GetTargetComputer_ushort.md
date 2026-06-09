# CSchedule::GetTargetComputer(ushort * *)

- ea: `0x180028490`
- end: `0x1800285a4`
- name: `?GetTargetComputer@CSchedule@@UEAAJPEAPEAG@Z`
- size: `276`
- prototype: `signed int __fastcall(CSchedule *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ef0`
- `0x180028490`
- `0x18002e572`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028529`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028529`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002851f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18002851f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180028552`

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
  Buffer = asc_180054B40[2];
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
0x180028490  mov     [rsp+arg_10], rbx
0x180028495  mov     [rsp+arg_18], rsi
0x18002849a  push    rdi
0x18002849b  sub     rsp, 250h
0x1800284a2  mov     rax, cs:__security_cookie
0x1800284a9  xor     rax, rsp
0x1800284ac  mov     [rsp+258h+var_18], rax
0x1800284b4  xor     esi, esi
0x1800284b6  mov     rdi, rdx
0x1800284b9  mov     rbx, rcx
0x1800284bc  test    rdx, rdx
0x1800284bf  jnz     short loc_1800284CB
0x1800284c1  mov     eax, 80070057h
0x1800284c6  jmp     loc_18002857F
0x1800284cb  mov     eax, dword ptr cs:asc_180054B40; "\\\\"
0x1800284d1  lea     rcx, [rsp+258h+var_222]; void *
0x1800284d6  mov     [rsp+258h+var_228], eax
0x1800284da  xor     edx, edx; Val
0x1800284dc  movzx   eax, word ptr cs:asc_180054B40+4; ""
0x1800284e3  mov     r8d, 200h; Size
0x1800284e9  mov     [rsp+258h+Buffer], ax
0x1800284ee  mov     [rsp+258h+nSize], 101h
0x1800284f6  call    memset_0
0x1800284fb  mov     rbx, [rbx+38h]
0x1800284ff  test    rbx, rbx
0x180028502  jz      short loc_180028515
0x180028504  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028508  inc     rax
0x18002850b  cmp     [rbx+rax*2], si
0x18002850f  jnz     short loc_180028508
0x180028511  inc     eax
0x180028513  jmp     short loc_180028549
0x180028515  lea     rdx, [rsp+258h+nSize]; nSize
0x18002851a  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18002851f  call    cs:__imp_GetComputerNameW
0x180028525  test    eax, eax
0x180028527  jnz     short loc_18002853D
0x180028529  call    cs:__imp_GetLastError
0x18002852f  test    eax, eax
0x180028531  jle     short loc_18002857F
0x180028533  movzx   eax, ax
0x180028536  or      eax, 80070000h
0x18002853b  jmp     short loc_18002857F
0x18002853d  mov     eax, [rsp+258h+nSize]
0x180028541  lea     rbx, [rsp+258h+var_228]
0x180028546  add     eax, 3
0x180028549  mov     ecx, eax
0x18002854b  add     rcx, rcx; cb
0x18002854e  mov     [rsp+258h+nSize], eax
0x180028552  call    cs:__imp_CoTaskMemAlloc
0x180028558  mov     [rdi], rax
0x18002855b  test    rax, rax
0x18002855e  jnz     short loc_180028567
0x180028560  mov     eax, 8007000Eh
0x180028565  jmp     short loc_18002857F
0x180028567  mov     edx, [rsp+258h+nSize]; unsigned __int64
0x18002856b  mov     r8, rbx; unsigned __int16 *
0x18002856e  mov     rcx, rax; unsigned __int16 *
0x180028571  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028576  test    eax, eax
0x180028578  mov     ecx, esi
0x18002857a  cmovs   ecx, eax
0x18002857d  mov     eax, ecx
0x18002857f  mov     rcx, [rsp+258h+var_18]
0x180028587  xor     rcx, rsp; StackCookie
0x18002858a  call    __security_check_cookie
0x18002858f  lea     r11, [rsp+258h+var_8]
0x180028597  mov     rbx, [r11+20h]
0x18002859b  mov     rsi, [r11+28h]
0x18002859f  mov     rsp, r11
0x1800285a2  pop     rdi
0x1800285a3  retn
```
