# CNetDiagHelperImpl::GetCacheTime(_FILETIME *)

- ea: `0x1800122a0`
- end: `0x1800122e2`
- name: `?GetCacheTime@CNetDiagHelperImpl@@UEAAJPEAU_FILETIME@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(CNetDiagHelperImpl *__hidden this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800122a0`
- `0x180012ca0`

## pseudocode

```c
__int64 __fastcall CNetDiagHelperImpl::GetCacheTime(CNetDiagHelperImpl *this, struct _FILETIME *a2)
{
  struct _FILETIME *v2; // rbx
  __int64 result; // rax

  v2 = a2;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *((_DWORD *)this + 4) != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  result = 8;
  do
  {
    LOBYTE(v2->dwLowDateTime) = 0;
    v2 = (struct _FILETIME *)((char *)v2 + 1);
    --result;
  }
  while ( result );
  return result;
}

```

## disassembly

```asm
0x1800122a0  mov     [rsp+arg_0], rbx
0x1800122a5  push    rdi
0x1800122a6  sub     rsp, 20h
0x1800122aa  mov     rbx, rdx
0x1800122ad  mov     rdi, rcx
0x1800122b0  test    rdx, rdx
0x1800122b3  jnz     short loc_1800122BA
0x1800122b5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800122ba  cmp     dword ptr [rdi+10h], 1
0x1800122be  jz      short loc_1800122C5
0x1800122c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800122c5  mov     eax, 8
0x1800122ca  mov     byte ptr [rbx], 0
0x1800122cd  inc     rbx
0x1800122d0  sub     rax, 1
0x1800122d4  jnz     short loc_1800122CA
0x1800122d6  mov     rbx, [rsp+28h+arg_0]
0x1800122db  add     rsp, 20h
0x1800122df  pop     rdi
0x1800122e0  retn
```
