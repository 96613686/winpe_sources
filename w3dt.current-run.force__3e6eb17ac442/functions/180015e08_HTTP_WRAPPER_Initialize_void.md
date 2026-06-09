# HTTP_WRAPPER::Initialize(void)

- ea: `0x180015e08`
- end: `0x180015e3b`
- name: `?Initialize@HTTP_WRAPPER@@QEAAKXZ`
- size: `51`
- prototype: `unsigned int __fastcall(HTTP_WRAPPER *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001060`
- `0x180012530`
- `0x1800143dc`

## callees

- `0x180015e08`

## import_xrefs

- `HTTPAPI!HttpInitialize` at `0x180015e24`
- `HTTPAPI!HttpInitialize` at `0x180015e24`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::Initialize(HTTP_WRAPPER *this)
{
  ULONG result; // eax

  result = HttpInitialize((HTTPAPI_VERSION)2, 1u, 0);
  if ( !result )
    *((_DWORD *)this + 3) = 1;
  return result;
}

```

## disassembly

```asm
0x180015e08  push    rbx
0x180015e0a  sub     rsp, 20h
0x180015e0e  xor     r8d, r8d; pReserved
0x180015e11  mov     dword ptr [rsp+28h+Version.HttpApiMajorVersion], 2
0x180015e19  mov     rbx, rcx
0x180015e1c  mov     ecx, dword ptr [rsp+28h+Version.HttpApiMajorVersion]; Version
0x180015e20  lea     edx, [r8+1]; Flags
0x180015e24  call    cs:__imp_HttpInitialize
0x180015e2a  test    eax, eax
0x180015e2c  jnz     short loc_180015E35
0x180015e2e  mov     dword ptr [rbx+0Ch], 1
0x180015e35  add     rsp, 20h
0x180015e39  pop     rbx
0x180015e3a  retn
```
