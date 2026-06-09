# UstCommon::CImpersonator::Impersonate(void *)

- ea: `0x18004eeb8`
- end: `0x18004ef4f`
- name: `?Impersonate@CImpersonator@UstCommon@@QEAAJPEAX@Z`
- size: `151`
- prototype: `int(UstCommon::CImpersonator *__hidden this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800313ac`

## callees

- `0x18004eeb8`
- `0x18004ef58`
- `0x18004f0ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eefe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004eefe`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004eeed`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004eeed`

## pseudocode

```c
__int64 __fastcall UstCommon::CImpersonator::Impersonate(UstCommon::CImpersonator *this, void *a2, __int64 a3)
{
  unsigned int v5; // ebx
  signed int LastError; // eax

  v5 = 1;
  if ( !*(_BYTE *)this && !UstCommon::CImpersonator::_IsThreadImpersonating(this) )
  {
    v5 = -2147024809;
    if ( a2 )
    {
      if ( ImpersonateLoggedOnUser(a2) )
      {
        *(_BYTE *)this = 1;
        v5 = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, v5);
  return v5;
}

```

## disassembly

```asm
0x18004eeb8  mov     [rsp+arg_0], rbx
0x18004eebd  mov     [rsp+arg_8], rsi
0x18004eec2  push    rdi
0x18004eec3  sub     rsp, 20h
0x18004eec7  cmp     byte ptr [rcx], 0
0x18004eeca  mov     rdi, rdx
0x18004eecd  mov     rsi, rcx
0x18004eed0  mov     ebx, 1
0x18004eed5  jnz     short loc_18004EF13
0x18004eed7  call    ?_IsThreadImpersonating@CImpersonator@UstCommon@@AEAA_NXZ; UstCommon::CImpersonator::_IsThreadImpersonating(void)
0x18004eedc  test    al, al
0x18004eede  jnz     short loc_18004EF13
0x18004eee0  mov     ebx, 80070057h
0x18004eee5  test    rdi, rdi
0x18004eee8  jz      short loc_18004EF13
0x18004eeea  mov     rcx, rdi; hToken
0x18004eeed  call    cs:__imp_ImpersonateLoggedOnUser
0x18004eef3  test    eax, eax
0x18004eef5  jz      short loc_18004EEFE
0x18004eef7  mov     byte ptr [rsi], 1
0x18004eefa  xor     ebx, ebx
0x18004eefc  jmp     short loc_18004EF13
0x18004eefe  call    cs:__imp_GetLastError
0x18004ef04  mov     ebx, eax
0x18004ef06  test    eax, eax
0x18004ef08  jle     short loc_18004EF13
0x18004ef0a  movzx   ebx, ax
0x18004ef0d  or      ebx, 80070000h
0x18004ef13  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef1a  lea     rax, WPP_GLOBAL_Control
0x18004ef21  cmp     rcx, rax
0x18004ef24  jz      short loc_18004EF3D
0x18004ef26  test    byte ptr [rcx+1Ch], 2
0x18004ef2a  jz      short loc_18004EF3D
0x18004ef2c  mov     rcx, [rcx+10h]
0x18004ef30  mov     edx, 0Dh
0x18004ef35  mov     r9d, ebx
0x18004ef38  call    WPP_SF_D
0x18004ef3d  mov     rsi, [rsp+28h+arg_8]
0x18004ef42  mov     eax, ebx
0x18004ef44  mov     rbx, [rsp+28h+arg_0]
0x18004ef49  add     rsp, 20h
0x18004ef4d  pop     rdi
0x18004ef4e  retn
```
