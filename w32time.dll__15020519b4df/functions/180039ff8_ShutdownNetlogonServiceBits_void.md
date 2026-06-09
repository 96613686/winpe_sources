# ShutdownNetlogonServiceBits(void)

- ea: `0x180039ff8`
- end: `0x18003a09f`
- name: `?ShutdownNetlogonServiceBits@@YAJXZ`
- size: `167`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180009a80`

## callees

- `0x180039ff8`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a06e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a06e`
- `logoncli!NetLogonSetServiceBits` at `0x18003a01e`
- `logoncli!NetLogonSetServiceBits` at `0x18003a01e`

## pseudocode

```c
signed int ShutdownNetlogonServiceBits(void)
{
  signed int result; // eax

  result = 0;
  dword_1800A468C = 0;
  if ( (dword_1800A45C0 & 0xFFFFFFFD) != 0 )
  {
    result = NetLogonSetServiceBits(0, 576, 0);
    if ( result == -1073610734 || !result )
    {
      if ( (unsigned int)((__int64 (__fastcall *)(struct SERVICE_STATUS_HANDLE__ *, __int64, _QWORD))fnW32TmI_ScSetServiceBits)(
                           g_servicestatushandle,
                           32,
                           0) )
        return 0;
      result = GetLastError();
      if ( result > 0 )
        result = (unsigned __int16)result | 0x80070000;
      if ( result == -2147024890 && g_servicestatushandle == (struct SERVICE_STATUS_HANDLE__ *)3 )
        return 0;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180039ff8  sub     rsp, 38h
0x180039ffc  xor     eax, eax
0x180039ffe  test    cs:dword_1800A45C0, 0FFFFFFFDh
0x18003a008  mov     cs:dword_1800A468C, eax
0x18003a00e  jz      loc_18003A099
0x18003a014  xor     r8d, r8d
0x18003a017  mov     edx, 240h
0x18003a01c  xor     ecx, ecx
0x18003a01e  call    cs:__imp_NetLogonSetServiceBits
0x18003a025  nop     dword ptr [rax+rax+00h]
0x18003a02a  cmp     eax, 0C0020012h
0x18003a02f  jz      short loc_18003A041
0x18003a031  test    eax, eax
0x18003a033  jz      short loc_18003A041
0x18003a035  jle     short loc_18003A099
0x18003a037  movzx   eax, ax
0x18003a03a  or      eax, 80070000h
0x18003a03f  jmp     short loc_18003A099
0x18003a041  mov     rcx, cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x18003a048  mov     r9d, 1
0x18003a04e  mov     rax, cs:?fnW32TmI_ScSetServiceBits@@3P6AHPEAUSERVICE_STATUS_HANDLE__@@KHHPEAG@ZEA; int (*fnW32TmI_ScSetServiceBits)(SERVICE_STATUS_HANDLE__ *,ulong,int,int,ushort *)
0x18003a055  xor     r8d, r8d
0x18003a058  mov     [rsp+38h+var_18], 0
0x18003a061  lea     edx, [r9+1Fh]
0x18003a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a06a  test    eax, eax
0x18003a06c  jnz     short loc_18003A097
0x18003a06e  call    cs:__imp_GetLastError
0x18003a075  nop     dword ptr [rax+rax+00h]
0x18003a07a  test    eax, eax
0x18003a07c  jle     short loc_18003A086
0x18003a07e  movzx   eax, ax
0x18003a081  or      eax, 80070000h
0x18003a086  cmp     eax, 80070006h
0x18003a08b  jnz     short loc_18003A099
0x18003a08d  cmp     cs:?g_servicestatushandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, 3; SERVICE_STATUS_HANDLE__ * g_servicestatushandle
0x18003a095  jnz     short loc_18003A099
0x18003a097  xor     eax, eax
0x18003a099  add     rsp, 38h
0x18003a09d  retn
```
