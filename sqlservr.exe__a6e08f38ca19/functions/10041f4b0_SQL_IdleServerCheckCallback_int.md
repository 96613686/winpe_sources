# SQL_IdleServerCheckCallback(int *)

- ea: `0x10041f4b0`
- end: `0x10041f4dc`
- name: `?SQL_IdleServerCheckCallback@@YAXPEAH@Z`
- size: `44`
- prototype: `void __fastcall(int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10041f4b0`

## import_xrefs

- `sqllang!?IsServiceBrokerIdle@@YAHXZ` at `0x10041f4ca`
- `sqllang!?IsServiceBrokerIdle@@YAHXZ` at `0x10041f4ca`
- `sqllang!?EndpointEnabled@DBMirroring@@SAHXZ` at `0x10041f4b9`
- `sqllang!?EndpointEnabled@DBMirroring@@SAHXZ` at `0x10041f4b9`

## pseudocode

```c
void __fastcall SQL_IdleServerCheckCallback(int *a1)
{
  if ( (unsigned int)DBMirroring::EndpointEnabled() == 1 )
    *a1 = 0;
  if ( !IsServiceBrokerIdle() )
    *a1 = 0;
}

```

## disassembly

```asm
0x10041f4b0  push    rbx
0x10041f4b2  sub     rsp, 20h
0x10041f4b6  mov     rbx, rcx
0x10041f4b9  call    cs:__imp_?EndpointEnabled@DBMirroring@@SAHXZ; DBMirroring::EndpointEnabled(void)
0x10041f4bf  cmp     eax, 1
0x10041f4c2  jnz     short loc_10041F4CA
0x10041f4c4  mov     dword ptr [rbx], 0
0x10041f4ca  call    cs:__imp_?IsServiceBrokerIdle@@YAHXZ; IsServiceBrokerIdle(void)
0x10041f4d0  test    eax, eax
0x10041f4d2  jnz     short loc_10041F4D6
0x10041f4d4  mov     [rbx], eax
0x10041f4d6  add     rsp, 20h
0x10041f4da  pop     rbx
0x10041f4db  retn
```
