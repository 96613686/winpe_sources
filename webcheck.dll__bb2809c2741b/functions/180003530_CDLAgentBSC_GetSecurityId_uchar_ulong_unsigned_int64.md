# CDLAgentBSC::GetSecurityId(uchar *,ulong *,unsigned __int64)

- ea: `0x180003530`
- end: `0x180003565`
- name: `?GetSecurityId@CDLAgentBSC@@UEAAJPEAEPEAK_K@Z`
- size: `53`
- prototype: `__int64 __fastcall(CDLAgentBSC *__hidden this, unsigned __int8 *, unsigned int *, unsigned __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003530`

## import_xrefs

- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x18000355a`
- `urlmon!__imp_GetZoneAgnosticSecurityIdFromUrl` at `0x18000355a`

## pseudocode

```c
__int64 __fastcall CDLAgentBSC::GetSecurityId(CDLAgentBSC *this, unsigned __int8 *a2, unsigned int *a3, __int64 a4)
{
  __int64 v4; // r10
  __int64 result; // rax

  v4 = *((_QWORD *)this + 526);
  result = 2147500037LL;
  if ( v4 )
    return GetZoneAgnosticSecurityIdFromUrl(v4, (char *)this + 36, a2, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180003530  sub     rsp, 38h
0x180003534  mov     r10, [rcx+1070h]
0x18000353b  mov     r11, rdx
0x18000353e  mov     eax, 80004005h
0x180003543  test    r10, r10
0x180003546  jz      short loc_180003560
0x180003548  mov     [rsp+38h+var_18], r9
0x18000354d  lea     rdx, [rcx+24h]
0x180003551  mov     r9, r8
0x180003554  mov     rcx, r10
0x180003557  mov     r8, r11
0x18000355a  call    cs:__imp_GetZoneAgnosticSecurityIdFromUrl
0x180003560  add     rsp, 38h
0x180003564  retn
```
