# HUBREG_DeleteUxdSettings

- ea: `0x1400858d8`
- end: `0x140085977`
- name: `HUBREG_DeleteUxdSettings`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140019204`
- `0x140081660`

## callees

- `0x140045570`
- `0x140085504`
- `0x140085668`
- `0x1400858d8`
- `0x1400878b0`

## pseudocode

```c
__int64 __fastcall HUBREG_DeleteUxdSettings(__int64 a1, int a2)
{
  __int64 v4; // rsi
  int v5; // edi
  bool v6; // zf

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         WdfDriverGlobals->Driver,
         off_14006B2C0);
  HUBREG_QueryGlobalUxdSettings(v4);
  v5 = a2 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 0;
    if ( !*(_DWORD *)(a1 + 1716) )
    {
      v6 = (*(_DWORD *)(v4 + 4) & 0x400) == 0;
      goto LABEL_7;
    }
LABEL_8:
    HUBREG_DeleteUxdPortKey(*(_QWORD *)a1, *(unsigned __int16 *)(*(_QWORD *)(a1 + 8) + 200LL));
    HUBREG_DeleteUxdDeviceKey(a1);
    return 0;
  }
  if ( *(_DWORD *)(a1 + 1712) == 1 )
    goto LABEL_8;
  v6 = (*(_DWORD *)(v4 + 4) & 0x200) == 0;
LABEL_7:
  if ( !v6 )
    goto LABEL_8;
  return 0;
}

```

## disassembly

```asm
0x1400858d8  mov     [rsp+arg_0], rbx
0x1400858dd  mov     [rsp+arg_8], rsi
0x1400858e2  push    rdi
0x1400858e3  sub     rsp, 20h
0x1400858e7  mov     rax, cs:WdfFunctions_01015
0x1400858ee  mov     rbx, rcx
0x1400858f1  mov     rcx, cs:WdfDriverGlobals
0x1400858f8  mov     edi, edx
0x1400858fa  mov     r8, cs:off_14006B2C0
0x140085901  mov     rax, [rax+650h]
0x140085908  mov     rdx, [rcx]
0x14008590b  call    _guard_dispatch_icall
0x140085910  mov     rcx, rax
0x140085913  mov     rsi, rax
0x140085916  call    HUBREG_QueryGlobalUxdSettings
0x14008591b  sub     edi, 1
0x14008591e  jz      short loc_140085937
0x140085920  cmp     edi, 1
0x140085923  jnz     short loc_140085964
0x140085925  cmp     dword ptr [rbx+6B4h], 0
0x14008592c  jnz     short loc_140085949
0x14008592e  test    dword ptr [rsi+4], 400h
0x140085935  jmp     short loc_140085947
0x140085937  cmp     dword ptr [rbx+6B0h], 1
0x14008593e  jz      short loc_140085949
0x140085940  test    dword ptr [rsi+4], 200h
0x140085947  jz      short loc_140085964
0x140085949  mov     rax, [rbx+8]
0x14008594d  mov     rcx, [rbx]
0x140085950  movzx   edx, word ptr [rax+0C8h]
0x140085957  call    HUBREG_DeleteUxdPortKey
0x14008595c  mov     rcx, rbx
0x14008595f  call    HUBREG_DeleteUxdDeviceKey
0x140085964  mov     rbx, [rsp+28h+arg_0]
0x140085969  xor     eax, eax
0x14008596b  mov     rsi, [rsp+28h+arg_8]
0x140085970  add     rsp, 20h
0x140085974  pop     rdi
0x140085975  retn
```
