# CDevNode::DevicePropertyExists(_DEVPROPKEY const &)

- ea: `0x18000a618`
- end: `0x18000a691`
- name: `?DevicePropertyExists@CDevNode@@QEAAEAEBU_DEVPROPKEY@@@Z`
- size: `121`
- prototype: `unsigned __int8 __fastcall(CDevNode *__hidden this, const struct _DEVPROPKEY *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007b44`
- `0x18000ace8`
- `0x18000aeac`
- `0x18000b240`
- `0x18000b280`
- `0x18000b2c0`

## callees

- `0x180008020`
- `0x18000a618`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a663`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000a65d`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18000a65d`

## pseudocode

```c
unsigned __int8 __fastcall CDevNode::DevicePropertyExists(CDevNode *this, const struct _DEVPROPKEY *a2)
{
  char *v3; // rdx
  __int64 v4; // rcx
  DWORD LastError; // eax
  int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  v3 = (char *)this + 16;
  v4 = *(_QWORD *)this;
  v7 = 0;
  DevObjGetDeviceProperty(v4, v3, a2, &v8, 0, 0, &v7, 0);
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError == 1168 )
      return 0;
    if ( LastError )
      CException::ThrowException(LastError, 0, 0);
  }
  return 1;
}

```

## disassembly

```asm
0x18000a618  mov     rax, rsp
0x18000a61b  sub     rsp, 48h
0x18000a61f  mov     dword ptr [rax-10h], 0
0x18000a626  mov     r8, rdx
0x18000a629  mov     dword ptr [rax+18h], 0
0x18000a630  lea     rdx, [rcx+10h]
0x18000a634  mov     rcx, [rcx]
0x18000a637  lea     r9, [rsp+48h+arg_10]
0x18000a63c  mov     dword ptr [rax+8], 0
0x18000a643  lea     rax, [rax+8]
0x18000a647  mov     [rsp+48h+var_18], rax
0x18000a64c  mov     [rsp+48h+var_20], 0
0x18000a654  mov     [rsp+48h+var_28], 0
0x18000a65d  call    cs:__imp_DevObjGetDeviceProperty
0x18000a663  call    cs:__imp_GetLastError
0x18000a669  cmp     eax, 7Ah ; 'z'
0x18000a66c  jz      short loc_18000A68A
0x18000a66e  cmp     eax, 490h
0x18000a673  jz      short loc_18000A686
0x18000a675  test    eax, eax
0x18000a677  jz      short loc_18000A68A
0x18000a679  xor     r8d, r8d
0x18000a67c  xor     edx, edx
0x18000a67e  mov     ecx, eax
0x18000a680  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x18000a686  xor     al, al
0x18000a688  jmp     short loc_18000A68C
0x18000a68a  mov     al, 1
0x18000a68c  add     rsp, 48h
0x18000a690  retn
```
