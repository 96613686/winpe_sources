# PolicyHelpers::IsPolicyConfiguredAndEnabled(tagUpdatePolicyValue_V1 *)

- ea: `0x18001f09c`
- end: `0x18001f0e6`
- name: `?IsPolicyConfiguredAndEnabled@PolicyHelpers@@SAHPEAUtagUpdatePolicyValue_V1@@@Z`
- size: `74`
- prototype: `__int64 __fastcall(struct tagUpdatePolicyValue_V1 *)`
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180016eb0`
- `0x180017014`
- `0x180017220`
- `0x180017804`
- `0x180017994`
- `0x180017b30`
- `0x180017bd0`
- `0x18001c88c`
- `0x18001d26c`

## callees

- `0x18001f09c`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001f0ce`
- `OLEAUT32!__imp_SysStringLen` at `0x18001f0ce`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::IsPolicyConfiguredAndEnabled(struct tagUpdatePolicyValue_V1 *a1)
{
  unsigned int v1; // ebx
  bool v2; // zf

  v1 = 0;
  if ( a1 && *((_DWORD *)a1 + 1) == 1 )
  {
    switch ( *((_WORD *)a1 + 8) )
    {
      case 3:
        v2 = *((_DWORD *)a1 + 6) == 0;
        goto LABEL_9;
      case 8:
        v2 = SysStringLen(*((BSTR *)a1 + 3)) == 0;
        goto LABEL_9;
      case 0x15:
        v2 = *((_QWORD *)a1 + 3) == 0;
LABEL_9:
        LOBYTE(v1) = !v2;
        break;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18001f09c  push    rbx
0x18001f09e  sub     rsp, 20h
0x18001f0a2  xor     ebx, ebx
0x18001f0a4  test    rcx, rcx
0x18001f0a7  jz      short loc_18001F0DE
0x18001f0a9  cmp     dword ptr [rcx+4], 1
0x18001f0ad  jnz     short loc_18001F0DE
0x18001f0af  cmp     word ptr [rcx+10h], 3
0x18001f0b4  jz      short loc_18001F0D8
0x18001f0b6  cmp     word ptr [rcx+10h], 8
0x18001f0bb  jz      short loc_18001F0CA
0x18001f0bd  cmp     word ptr [rcx+10h], 15h
0x18001f0c2  jnz     short loc_18001F0DE
0x18001f0c4  cmp     [rcx+18h], rbx
0x18001f0c8  jmp     short loc_18001F0DB
0x18001f0ca  mov     rcx, [rcx+18h]; pbstr
0x18001f0ce  call    cs:__imp_SysStringLen
0x18001f0d4  test    eax, eax
0x18001f0d6  jmp     short loc_18001F0DB
0x18001f0d8  cmp     [rcx+18h], ebx
0x18001f0db  setnz   bl
0x18001f0de  mov     eax, ebx
0x18001f0e0  add     rsp, 20h
0x18001f0e4  pop     rbx
0x18001f0e5  retn
```
