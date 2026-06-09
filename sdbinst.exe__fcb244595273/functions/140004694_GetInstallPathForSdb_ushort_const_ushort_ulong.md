# GetInstallPathForSdb(ushort const *,ushort *,ulong)

- ea: `0x140004694`
- end: `0x1400046ec`
- name: `?GetInstallPathForSdb@@YAHPEBGPEAGK@Z`
- size: `88`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140004df8`
- `0x140008500`

## callees

- `0x1400045e0`
- `0x140004694`
- `0x140012be0`
- `0x14002e420`

## pseudocode

```c
__int64 __fastcall GetInstallPathForSdb(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 result; // rax
  __int64 v4; // rdx
  struct _GUID v5; // [rsp+20h] [rbp-28h] BYREF

  v5 = 0;
  result = GetGuid(a1, &v5);
  if ( (_DWORD)result )
  {
    result = SdbGetPathCustomSdb(a2, v4, &v5);
    if ( (_DWORD)result )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140004694  push    rbx
0x140004696  sub     rsp, 40h
0x14000469a  mov     rax, cs:__security_cookie
0x1400046a1  xor     rax, rsp
0x1400046a4  mov     [rsp+48h+var_18], rax
0x1400046a9  mov     rbx, rdx
0x1400046ac  xorps   xmm0, xmm0
0x1400046af  lea     rdx, [rsp+48h+var_28]; struct _GUID *
0x1400046b4  movups  xmmword ptr [rsp+48h+var_28.Data1], xmm0
0x1400046b9  call    ?GetGuid@@YAHPEBGPEAU_GUID@@@Z; GetGuid(ushort const *,_GUID *)
0x1400046be  test    eax, eax
0x1400046c0  jz      short loc_1400046D9
0x1400046c2  lea     r8, [rsp+48h+var_28]
0x1400046c7  mov     rcx, rbx
0x1400046ca  call    SdbGetPathCustomSdb
0x1400046cf  test    eax, eax
0x1400046d1  mov     ecx, 1
0x1400046d6  cmovnz  eax, ecx
0x1400046d9  mov     rcx, [rsp+48h+var_18]
0x1400046de  xor     rcx, rsp; StackCookie
0x1400046e1  call    __security_check_cookie
0x1400046e6  add     rsp, 40h
0x1400046ea  pop     rbx
0x1400046eb  retn
```
