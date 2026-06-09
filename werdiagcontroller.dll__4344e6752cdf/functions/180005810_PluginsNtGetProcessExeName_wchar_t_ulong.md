# PluginsNtGetProcessExeName(wchar_t *,ulong)

- ea: `0x180005810`
- end: `0x180005989`
- name: `?PluginsNtGetProcessExeName@@YAJPEA_WK@Z`
- size: `377`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800028d0`

## callees

- `0x180001400`
- `0x180001cc6`
- `0x180005810`
- `0x1800061b4`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18000587c`
- `ntdll!DbgPrintEx` at `0x18000587c`
- `ntdll!NtQueryInformationProcess` at `0x18000585f`
- `ntdll!NtQueryInformationProcess` at `0x18000585f`

## string_xrefs

- `0x180005958`: `WERDIAG: Failed copying string. NTSTATUS: %08X\n`

## pseudocode

```c
__int64 __fastcall PluginsNtGetProcessExeName(wchar_t *a1)
{
  NTSTATUS v1; // eax
  unsigned int v2; // ebx
  unsigned __int16 v3; // ax
  WCHAR *v4; // rcx
  unsigned __int64 v5; // rax
  __int64 v6; // r8
  WCHAR *v7; // r9
  __int64 v8; // rax
  WCHAR *v9; // r8
  __int64 v10; // rdx
  WCHAR *v11; // rcx
  unsigned __int16 ProcessInformation; // [rsp+30h] [rbp-238h] BYREF
  char v14[6]; // [rsp+32h] [rbp-236h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-230h]

  ProcessInformation = 0;
  memset_0(v14, 0, 0x216u);
  v1 = NtQueryInformationProcess(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         ProcessImageFileNameWin32,
         &ProcessInformation,
         0x218u,
         0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v3 = ProcessInformation;
    if ( ProcessInformation <= 0x208u
      || (MicrosoftTelemetryAssertTriggeredNoArgs(), v3 = ProcessInformation, ProcessInformation <= 0x208u) )
    {
      *(_WORD *)(v15 + 2 * ((unsigned __int64)v3 >> 1)) = 0;
      v4 = (WCHAR *)(v15 + 2 * ((unsigned __int64)ProcessInformation >> 1));
      while ( 1 )
      {
        v7 = v4;
        if ( (unsigned __int64)v4 <= v15 )
          break;
        v5 = *--v4;
        LOWORD(v5) = v5 - 47;
        if ( (unsigned __int16)v5 <= 0x2Du )
        {
          v6 = 0x200000000801LL;
          if ( _bittest64(&v6, v5) )
            break;
        }
      }
      v8 = 2147483646;
      v9 = &g_SettingsEngine;
      v10 = 260;
      do
      {
        if ( !v8 )
          break;
        if ( !*v7 )
          break;
        *v9++ = *v7++;
        --v8;
        --v10;
      }
      while ( v10 );
      v11 = v9 - 1;
      v2 = v10 == 0 ? 0x80000005 : 0;
      if ( v10 )
        v11 = v9;
      *v11 = 0;
      if ( v10 )
        return 0;
      else
        DbgPrintEx(0x96u, 0, "WERDIAG: Failed copying string. NTSTATUS: %08X\n", v2);
    }
    else
    {
      v2 = -1073741823;
      DbgPrintEx(0x96u, 0, "WERDIAG: Invalid size returned. NTSTATUS: %08X\n", 3221225473LL);
    }
  }
  else
  {
    DbgPrintEx(0x96u, 0, "WERDIAG: NtQueryInformationProcess failed. NTSTATUS: %08X\n", (unsigned int)v1);
  }
  return v2;
}

```

## disassembly

```asm
0x180005810  mov     [rsp+arg_0], rbx
0x180005815  push    rdi
0x180005816  sub     rsp, 260h
0x18000581d  mov     rax, cs:__security_cookie
0x180005824  xor     rax, rsp
0x180005827  mov     [rsp+268h+var_18], rax
0x18000582f  xor     edi, edi
0x180005831  lea     rcx, [rsp+268h+var_236]; void *
0x180005836  xor     edx, edx; Val
0x180005838  mov     [rsp+268h+ProcessInformation], di
0x18000583d  mov     r8d, 216h; Size
0x180005843  call    memset_0
0x180005848  mov     r9d, 218h; ProcessInformationLength
0x18000584e  mov     [rsp+268h+ReturnLength], rdi; ReturnLength
0x180005853  lea     r8, [rsp+268h+ProcessInformation]; ProcessInformation
0x180005858  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000585c  lea     edx, [rdi+2Bh]; ProcessInformationClass
0x18000585f  call    cs:__imp_NtQueryInformationProcess
0x180005865  mov     ebx, eax
0x180005867  test    eax, eax
0x180005869  jns     short loc_180005887
0x18000586b  mov     r9d, eax
0x18000586e  lea     r8, aWerdiagNtquery_0; "WERDIAG: NtQueryInformationProcess fail"...
0x180005875  xor     edx, edx; Level
0x180005877  mov     ecx, 96h; ComponentId
0x18000587c  call    cs:__imp_DbgPrintEx
0x180005882  jmp     loc_180005966
0x180005887  movzx   eax, [rsp+268h+ProcessInformation]
0x18000588c  mov     ebx, 208h
0x180005891  cmp     ax, bx
0x180005894  jbe     short loc_1800058B6
0x180005896  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000589b  movzx   eax, [rsp+268h+ProcessInformation]
0x1800058a0  cmp     ax, bx
0x1800058a3  jbe     short loc_1800058B6
0x1800058a5  mov     ebx, 0C0000001h
0x1800058aa  lea     r8, aWerdiagInvalid_4; "WERDIAG: Invalid size returned. NTSTATU"...
0x1800058b1  mov     r9d, ebx
0x1800058b4  jmp     short loc_180005875
0x1800058b6  movzx   edx, ax
0x1800058b9  mov     rax, [rsp+268h+var_230]
0x1800058be  shr     rdx, 1
0x1800058c1  mov     [rax+rdx*2], di
0x1800058c5  movzx   eax, [rsp+268h+ProcessInformation]
0x1800058ca  mov     rdx, [rsp+268h+var_230]
0x1800058cf  shr     rax, 1
0x1800058d2  lea     rcx, [rdx+rax*2]
0x1800058d6  jmp     short loc_1800058F9
0x1800058d8  sub     rcx, 2
0x1800058dc  movzx   eax, word ptr [rcx]
0x1800058df  sub     ax, 2Fh ; '/'
0x1800058e3  cmp     ax, 2Dh ; '-'
0x1800058e7  ja      short loc_1800058F9
0x1800058e9  mov     r8, 200000000801h
0x1800058f3  bt      r8, rax
0x1800058f7  jb      short loc_180005901
0x1800058f9  mov     r9, rcx
0x1800058fc  cmp     rcx, rdx
0x1800058ff  ja      short loc_1800058D8
0x180005901  mov     eax, 7FFFFFFEh
0x180005906  lea     r8, ?g_SettingsEngine@@3VCAutoVerifierSettingsEngine@@A; CAutoVerifierSettingsEngine g_SettingsEngine
0x18000590d  mov     edx, 104h
0x180005912  test    rax, rax
0x180005915  jz      short loc_180005935
0x180005917  movzx   ecx, word ptr [r9]
0x18000591b  test    cx, cx
0x18000591e  jz      short loc_180005935
0x180005920  mov     [r8], cx
0x180005924  add     r9, 2
0x180005928  add     r8, 2
0x18000592c  dec     rax
0x18000592f  sub     rdx, 1
0x180005933  jnz     short loc_180005912
0x180005935  mov     rax, rdx
0x180005938  lea     rcx, [r8-2]
0x18000593c  neg     rax
0x18000593f  sbb     ebx, ebx
0x180005941  not     ebx
0x180005943  and     ebx, 80000005h
0x180005949  test    rdx, rdx
0x18000594c  cmovnz  rcx, r8
0x180005950  mov     [rcx], di
0x180005953  jnz     short loc_180005964
0x180005955  mov     r9d, ebx
0x180005958  lea     r8, aWerdiagFailedC_4; "WERDIAG: Failed copying string. NTSTATU"...
0x18000595f  jmp     loc_180005875
0x180005964  mov     ebx, edi
0x180005966  mov     eax, ebx
0x180005968  mov     rcx, [rsp+268h+var_18]
0x180005970  xor     rcx, rsp; StackCookie
0x180005973  call    __security_check_cookie
0x180005978  mov     rbx, [rsp+268h+arg_0]
0x180005980  add     rsp, 260h
0x180005987  pop     rdi
0x180005988  retn
```
