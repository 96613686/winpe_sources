# CalcMX(_SSDP_REQUEST *)

- ea: `0x180031e20`
- end: `0x180031ee7`
- name: `?CalcMX@@YAJPEAU_SSDP_REQUEST@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800040e0`

## callees

- `0x180031e20`
- `0x180037db4`
- `0x180037dc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180031ebd`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x180031ebd`

## string_xrefs

- `0x180031e83`: `urn:schemas-upnp-org:service:`

## pseudocode

```c
__int64 __fastcall CalcMX(struct _SSDP_REQUEST *a1)
{
  __int64 v1; // rdi
  const char *v2; // rbx
  int v3; // ebx
  int v4; // eax
  int v5; // ecx
  __int64 result; // rax

  v1 = *((_QWORD *)a1 + 10);
  v2 = *(const char **)(v1 + 24);
  if ( !strncmp_0(v2, "uuid:", 5u) )
  {
    v3 = 1;
  }
  else if ( !strcmp_0(v2, "upnp:rootdevice") || !strcmp_0(v2, "ssdp:all") )
  {
    v3 = 3;
  }
  else if ( !strncmp_0(v2, "urn:schemas-upnp-org:service:", 0x1Du)
         || (v4 = strncmp_0(v2, "urn:schemas-upnp-org:device:", 0x1Cu), v3 = 1, !v4) )
  {
    v3 = 2;
  }
  v5 = atol(*(const char **)(v1 + 40));
  result = 12;
  if ( v5 <= 12 )
  {
    result = (unsigned int)v5;
    if ( v5 < v3 )
      return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x180031e20  mov     [rsp+arg_0], rbx
0x180031e25  push    rdi
0x180031e26  sub     rsp, 20h
0x180031e2a  mov     rdi, [rcx+50h]
0x180031e2e  lea     rdx, aUuid; "uuid:"
0x180031e35  mov     r8d, 5; MaxCount
0x180031e3b  mov     rbx, [rdi+18h]
0x180031e3f  mov     rcx, rbx; Str1
0x180031e42  call    strncmp_0
0x180031e47  test    eax, eax
0x180031e49  jnz     short loc_180031E50
0x180031e4b  lea     ebx, [rax+1]
0x180031e4e  jmp     short loc_180031EB9
0x180031e50  lea     rdx, aUpnpRootdevice; "upnp:rootdevice"
0x180031e57  mov     rcx, rbx; Str1
0x180031e5a  call    strcmp_0
0x180031e5f  test    eax, eax
0x180031e61  jz      short loc_180031E76
0x180031e63  lea     rdx, aSsdpAll; "ssdp:all"
0x180031e6a  mov     rcx, rbx; Str1
0x180031e6d  call    strcmp_0
0x180031e72  test    eax, eax
0x180031e74  jnz     short loc_180031E7D
0x180031e76  mov     ebx, 3
0x180031e7b  jmp     short loc_180031EB9
0x180031e7d  mov     r8d, 1Dh; MaxCount
0x180031e83  lea     rdx, aUrnSchemasUpnp_0; "urn:schemas-upnp-org:service:"
0x180031e8a  mov     rcx, rbx; Str1
0x180031e8d  call    strncmp_0
0x180031e92  test    eax, eax
0x180031e94  jz      short loc_180031EB4
0x180031e96  mov     r8d, 1Ch; MaxCount
0x180031e9c  lea     rdx, aUrnSchemasUpnp; "urn:schemas-upnp-org:device:"
0x180031ea3  mov     rcx, rbx; Str1
0x180031ea6  call    strncmp_0
0x180031eab  mov     ebx, 1
0x180031eb0  test    eax, eax
0x180031eb2  jnz     short loc_180031EB9
0x180031eb4  mov     ebx, 2
0x180031eb9  mov     rcx, [rdi+28h]; String
0x180031ebd  call    cs:__imp_atol
0x180031ec4  nop     dword ptr [rax+rax+00h]
0x180031ec9  mov     ecx, eax
0x180031ecb  mov     eax, 0Ch
0x180031ed0  cmp     ecx, eax
0x180031ed2  jg      short loc_180031EDB
0x180031ed4  cmp     ecx, ebx
0x180031ed6  mov     eax, ecx
0x180031ed8  cmovl   eax, ebx
0x180031edb  mov     rbx, [rsp+28h+arg_0]
0x180031ee0  add     rsp, 20h
0x180031ee4  pop     rdi
0x180031ee5  retn
```
