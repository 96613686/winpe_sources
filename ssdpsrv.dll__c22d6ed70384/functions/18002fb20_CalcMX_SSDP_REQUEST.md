# CalcMX(_SSDP_REQUEST *)

- ea: `0x18002fb20`
- end: `0x18002fbe0`
- name: `?CalcMX@@YAJPEAU_SSDP_REQUEST@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct _SSDP_REQUEST *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800029b0`

## callees

- `0x18002fb20`
- `0x180035274`
- `0x180035280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x18002fbbd`
- `api-ms-win-crt-private-l1-1-0!_o_atol` at `0x18002fbbd`

## string_xrefs

- `0x18002fb83`: `urn:schemas-upnp-org:service:`

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
0x18002fb20  mov     [rsp+arg_0], rbx
0x18002fb25  push    rdi
0x18002fb26  sub     rsp, 20h
0x18002fb2a  mov     rdi, [rcx+50h]
0x18002fb2e  lea     rdx, aUuid; "uuid:"
0x18002fb35  mov     r8d, 5; MaxCount
0x18002fb3b  mov     rbx, [rdi+18h]
0x18002fb3f  mov     rcx, rbx; Str1
0x18002fb42  call    strncmp_0
0x18002fb47  test    eax, eax
0x18002fb49  jnz     short loc_18002FB50
0x18002fb4b  lea     ebx, [rax+1]
0x18002fb4e  jmp     short loc_18002FBB9
0x18002fb50  lea     rdx, aUpnpRootdevice; "upnp:rootdevice"
0x18002fb57  mov     rcx, rbx; Str1
0x18002fb5a  call    strcmp_0
0x18002fb5f  test    eax, eax
0x18002fb61  jz      short loc_18002FB76
0x18002fb63  lea     rdx, Str2; "ssdp:all"
0x18002fb6a  mov     rcx, rbx; Str1
0x18002fb6d  call    strcmp_0
0x18002fb72  test    eax, eax
0x18002fb74  jnz     short loc_18002FB7D
0x18002fb76  mov     ebx, 3
0x18002fb7b  jmp     short loc_18002FBB9
0x18002fb7d  mov     r8d, 1Dh; MaxCount
0x18002fb83  lea     rdx, aUrnSchemasUpnp_0; "urn:schemas-upnp-org:service:"
0x18002fb8a  mov     rcx, rbx; Str1
0x18002fb8d  call    strncmp_0
0x18002fb92  test    eax, eax
0x18002fb94  jz      short loc_18002FBB4
0x18002fb96  mov     r8d, 1Ch; MaxCount
0x18002fb9c  lea     rdx, aUrnSchemasUpnp; "urn:schemas-upnp-org:device:"
0x18002fba3  mov     rcx, rbx; Str1
0x18002fba6  call    strncmp_0
0x18002fbab  mov     ebx, 1
0x18002fbb0  test    eax, eax
0x18002fbb2  jnz     short loc_18002FBB9
0x18002fbb4  mov     ebx, 2
0x18002fbb9  mov     rcx, [rdi+28h]; String
0x18002fbbd  call    cs:__imp_atol
0x18002fbc3  mov     ecx, eax
0x18002fbc5  mov     eax, 0Ch
0x18002fbca  cmp     ecx, eax
0x18002fbcc  jg      short loc_18002FBD5
0x18002fbce  cmp     ecx, ebx
0x18002fbd0  mov     eax, ecx
0x18002fbd2  cmovl   eax, ebx
0x18002fbd5  mov     rbx, [rsp+28h+arg_0]
0x18002fbda  add     rsp, 20h
0x18002fbde  pop     rdi
0x18002fbdf  retn
```
