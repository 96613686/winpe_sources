# Buffer::Advance(ulong)

- ea: `0x18000b540`
- end: `0x18000b5f8`
- name: `?Advance@Buffer@@UEAAXK@Z`
- size: `184`
- prototype: `void __fastcall(Buffer *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006818`

## callees

- `0x180001aac`
- `0x1800025d0`
- `0x1800027ac`
- `0x18000b540`
- `0x18000b6b8`
- `0x18000b804`

## string_xrefs

- `0x18000b5d3`: `admin\wmi\events\forwarding\common\buffer.cpp`

## pseudocode

```c
void __fastcall Buffer::Advance(Buffer *this, unsigned int a2)
{
  unsigned int v4; // edx
  int v5; // ecx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v4 = *((_DWORD *)this + 6) + a2;
  if ( v4 < *((_DWORD *)this + 6) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids, 13);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0xDu,
      "admin\\wmi\\events\\forwarding\\common\\buffer.cpp",
      102);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( v4 > *((_DWORD *)this + 2) )
    Buffer::SetSize(this, v4);
  if ( !*((_QWORD *)this + 2) || a2 > 0x10000000 || (v5 = *((_DWORD *)this + 6), a2 > *((_DWORD *)this + 2) - v5) )
    UserBuffer::ThrowUnexpectedEOFException();
  *((_DWORD *)this + 6) = v5 + a2;
}

```

## disassembly

```asm
0x18000b540  mov     [rsp+arg_0], rbx
0x18000b545  push    rdi
0x18000b546  sub     rsp, 60h
0x18000b54a  mov     edi, edx
0x18000b54c  mov     rbx, rcx
0x18000b54f  add     edx, [rcx+18h]; unsigned int
0x18000b552  cmp     edx, [rcx+18h]
0x18000b555  jb      short loc_18000B593
0x18000b557  cmp     edx, [rcx+8]
0x18000b55a  jbe     short loc_18000B561
0x18000b55c  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18000b561  cmp     qword ptr [rbx+10h], 0
0x18000b566  jz      short loc_18000B58D
0x18000b568  cmp     edi, 10000000h
0x18000b56e  ja      short loc_18000B58D
0x18000b570  mov     eax, [rbx+8]
0x18000b573  mov     ecx, [rbx+18h]
0x18000b576  sub     eax, ecx
0x18000b578  cmp     edi, eax
0x18000b57a  ja      short loc_18000B58D
0x18000b57c  lea     eax, [rcx+rdi]
0x18000b57f  mov     [rbx+18h], eax
0x18000b582  mov     rbx, [rsp+68h+arg_0]
0x18000b587  add     rsp, 60h
0x18000b58b  pop     rdi
0x18000b58c  retn
0x18000b58d  call    ?ThrowUnexpectedEOFException@UserBuffer@@CAXXZ; UserBuffer::ThrowUnexpectedEOFException(void)
0x18000b593  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b59a  lea     rax, WPP_GLOBAL_Control
0x18000b5a1  mov     ebx, 0Dh
0x18000b5a6  cmp     rcx, rax
0x18000b5a9  jz      short loc_18000B5CD
0x18000b5ab  test    byte ptr [rcx+1Ch], 1
0x18000b5af  jz      short loc_18000B5CD
0x18000b5b1  cmp     byte ptr [rcx+19h], 2
0x18000b5b5  jb      short loc_18000B5CD
0x18000b5b7  mov     rcx, [rcx+10h]
0x18000b5bb  lea     edx, [rbx-1]
0x18000b5be  mov     r9d, ebx
0x18000b5c1  lea     r8, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids
0x18000b5c8  call    WPP_SF_D
0x18000b5cd  mov     r9d, 66h ; 'f'; int
0x18000b5d3  lea     r8, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x18000b5da  mov     edx, ebx; unsigned int
0x18000b5dc  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000b5e1  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b5e6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b5ed  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b5f2  call    _CxxThrowException_0
```
