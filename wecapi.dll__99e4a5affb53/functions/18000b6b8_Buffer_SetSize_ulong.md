# Buffer::SetSize(ulong)

- ea: `0x18000b6b8`
- end: `0x18000b7fb`
- name: `?SetSize@Buffer@@QEAAXK@Z`
- size: `323`
- prototype: `void __fastcall(Buffer *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b540`
- `0x18000b680`
- `0x18000b880`

## callees

- `0x180001aac`
- `0x180001ac6`
- `0x1800025d0`
- `0x18000262c`
- `0x1800026c0`
- `0x1800027ac`
- `0x18000b6b8`

## string_xrefs

- `0x18000b772`: `admin\wmi\events\forwarding\common\buffer.cpp`
- `0x18000b7d6`: `admin\wmi\events\forwarding\common\buffer.cpp`

## pseudocode

```c
void __fastcall Buffer::SetSize(Buffer *this, unsigned int a2)
{
  unsigned int v3; // ecx
  SIZE_T v4; // rcx
  int v5; // esi
  void *v6; // rax
  void *v7; // rdi
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = *((_DWORD *)this + 2);
  if ( a2 > v3 )
  {
    if ( a2 > 0x10000000 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids, 13);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0xDu,
        "admin\\wmi\\events\\forwarding\\common\\buffer.cpp",
        113);
      throw (wmi::GenericException *)pExceptionObject;
    }
    v4 = 2 * v3;
    if ( (unsigned int)v4 <= a2 )
      v4 = a2 + 256;
    v5 = v4;
    v6 = operator new(v4);
    v7 = v6;
    if ( !v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids, 14);
      }
      wmi::GenericException::GenericException(
        (wmi::GenericException *)pExceptionObject,
        0xEu,
        "admin\\wmi\\events\\forwarding\\common\\buffer.cpp",
        121);
      throw (wmi::GenericException *)pExceptionObject;
    }
    memcpy_0(v6, *((const void **)this + 2), *((unsigned int *)this + 6));
    if ( *((_BYTE *)this + 32) )
      operator delete(*((void **)this + 2));
    *((_DWORD *)this + 2) = v5;
    *((_QWORD *)this + 2) = v7;
    *((_BYTE *)this + 32) = 1;
  }
}

```

## disassembly

```asm
0x18000b6b8  mov     [rsp+arg_0], rbx
0x18000b6bd  mov     [rsp+arg_8], rsi
0x18000b6c2  push    rdi
0x18000b6c3  sub     rsp, 60h
0x18000b6c7  mov     rbx, rcx
0x18000b6ca  mov     ecx, [rcx+8]
0x18000b6cd  cmp     edx, ecx
0x18000b6cf  jbe     short loc_18000B723
0x18000b6d1  cmp     edx, 10000000h
0x18000b6d7  ja      loc_18000B797
0x18000b6dd  add     ecx, ecx
0x18000b6df  lea     eax, [rdx+100h]
0x18000b6e5  cmp     ecx, edx
0x18000b6e7  cmovbe  ecx, eax; dwBytes
0x18000b6ea  mov     esi, ecx
0x18000b6ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b6f1  mov     rdi, rax
0x18000b6f4  test    rax, rax
0x18000b6f7  jz      short loc_18000B733
0x18000b6f9  mov     r8d, [rbx+18h]; Size
0x18000b6fd  mov     rcx, rax; void *
0x18000b700  mov     rdx, [rbx+10h]; Src
0x18000b704  call    memcpy_0
0x18000b709  cmp     byte ptr [rbx+20h], 0
0x18000b70d  jz      short loc_18000B718
0x18000b70f  mov     rcx, [rbx+10h]; void *
0x18000b713  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b718  mov     [rbx+8], esi
0x18000b71b  mov     [rbx+10h], rdi
0x18000b71f  mov     byte ptr [rbx+20h], 1
0x18000b723  mov     rbx, [rsp+68h+arg_0]
0x18000b728  mov     rsi, [rsp+68h+arg_8]
0x18000b72d  add     rsp, 60h
0x18000b731  pop     rdi
0x18000b732  retn
0x18000b733  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b73a  lea     rax, WPP_GLOBAL_Control
0x18000b741  mov     ebx, 0Eh
0x18000b746  cmp     rcx, rax
0x18000b749  jz      short loc_18000B76C
0x18000b74b  test    byte ptr [rcx+1Ch], 1
0x18000b74f  jz      short loc_18000B76C
0x18000b751  cmp     byte ptr [rcx+19h], 2
0x18000b755  jb      short loc_18000B76C
0x18000b757  mov     rcx, [rcx+10h]
0x18000b75b  lea     r8, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids
0x18000b762  mov     edx, ebx
0x18000b764  mov     r9d, ebx
0x18000b767  call    WPP_SF_D
0x18000b76c  mov     r9d, 79h ; 'y'; int
0x18000b772  lea     r8, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x18000b779  mov     edx, ebx; unsigned int
0x18000b77b  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000b780  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b785  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b78c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b791  call    _CxxThrowException_0
0x18000b797  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b79e  lea     rax, WPP_GLOBAL_Control
0x18000b7a5  mov     ebx, 0Dh
0x18000b7aa  cmp     rcx, rax
0x18000b7ad  jz      short loc_18000B7D0
0x18000b7af  test    byte ptr [rcx+1Ch], 1
0x18000b7b3  jz      short loc_18000B7D0
0x18000b7b5  cmp     byte ptr [rcx+19h], 2
0x18000b7b9  jb      short loc_18000B7D0
0x18000b7bb  mov     rcx, [rcx+10h]
0x18000b7bf  lea     r8, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids
0x18000b7c6  mov     edx, ebx
0x18000b7c8  mov     r9d, ebx
0x18000b7cb  call    WPP_SF_D
0x18000b7d0  mov     r9d, 71h ; 'q'; int
0x18000b7d6  lea     r8, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x18000b7dd  mov     edx, ebx; unsigned int
0x18000b7df  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000b7e4  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b7e9  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b7f0  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b7f5  call    _CxxThrowException_0
```
