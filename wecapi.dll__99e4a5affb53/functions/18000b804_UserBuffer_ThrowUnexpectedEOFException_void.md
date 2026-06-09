# UserBuffer::ThrowUnexpectedEOFException(void)

- ea: `0x18000b804`
- end: `0x18000b86d`
- name: `?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ`
- size: `105`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b540`
- `0x18000b620`
- `0x18000b680`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x18000b804`

## string_xrefs

- `0x18000b846`: `admin\wmi\events\forwarding\common\buffer.cpp`

## pseudocode

```c
void __noreturn UserBuffer::ThrowUnexpectedEOFException(void)
{
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids, 13);
  }
  wmi::GenericException::GenericException(
    (wmi::GenericException *)pExceptionObject,
    0xDu,
    "admin\\wmi\\events\\forwarding\\common\\buffer.cpp",
    14);
  throw (wmi::GenericException *)pExceptionObject;
}

```

## disassembly

```asm
0x18000b804  sub     rsp, 68h
0x18000b808  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b80f  lea     rax, WPP_GLOBAL_Control
0x18000b816  cmp     rcx, rax
0x18000b819  jz      short loc_18000B840
0x18000b81b  test    byte ptr [rcx+1Ch], 1
0x18000b81f  jz      short loc_18000B840
0x18000b821  cmp     byte ptr [rcx+19h], 2
0x18000b825  jb      short loc_18000B840
0x18000b827  mov     rcx, [rcx+10h]
0x18000b82b  lea     r8, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids
0x18000b832  mov     edx, 0Ah
0x18000b837  lea     r9d, [rdx+3]
0x18000b83b  call    WPP_SF_D
0x18000b840  mov     r9d, 0Eh; int
0x18000b846  lea     r8, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x18000b84d  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000b852  lea     edx, [r9-1]; unsigned int
0x18000b856  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b85b  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b862  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b867  call    _CxxThrowException_0
```
