# Buffer::Write(void * const,ulong)

- ea: `0x18000b880`
- end: `0x18000b936`
- name: `?Write@Buffer@@UEAAXQEAXK@Z`
- size: `182`
- prototype: `void __fastcall(Buffer *this, void *const, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006818`

## callees

- `0x180001aac`
- `0x180001ac6`
- `0x1800025d0`
- `0x1800027ac`
- `0x18000b6b8`
- `0x18000b880`

## string_xrefs

- `0x18000b911`: `admin\wmi\events\forwarding\common\buffer.cpp`

## pseudocode

```c
void __fastcall Buffer::Write(Buffer *this, void *const a2, unsigned int a3)
{
  unsigned int v3; // eax
  size_t v5; // rdi
  unsigned int v7; // edx
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  v3 = *((_DWORD *)this + 6);
  v5 = a3;
  v7 = v3 + a3;
  if ( v3 + a3 < v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids, 13);
    }
    wmi::GenericException::GenericException(
      (wmi::GenericException *)pExceptionObject,
      0xDu,
      "admin\\wmi\\events\\forwarding\\common\\buffer.cpp",
      86);
    throw (wmi::GenericException *)pExceptionObject;
  }
  if ( v7 > *((_DWORD *)this + 2) )
    Buffer::SetSize(this, v7);
  memcpy_0((void *)(*((_QWORD *)this + 2) + *((unsigned int *)this + 6)), a2, v5);
  *((_DWORD *)this + 6) += v5;
}

```

## disassembly

```asm
0x18000b880  mov     [rsp+arg_0], rbx
0x18000b885  mov     [rsp+arg_8], rsi
0x18000b88a  push    rdi
0x18000b88b  sub     rsp, 60h
0x18000b88f  mov     eax, [rcx+18h]
0x18000b892  mov     rsi, rdx
0x18000b895  mov     edi, r8d
0x18000b898  mov     rbx, rcx
0x18000b89b  lea     edx, [rax+rdi]; unsigned int
0x18000b89e  cmp     edx, eax
0x18000b8a0  jb      short loc_18000B8D1
0x18000b8a2  cmp     edx, [rcx+8]
0x18000b8a5  jbe     short loc_18000B8AC
0x18000b8a7  call    ?SetSize@Buffer@@QEAAXK@Z; Buffer::SetSize(ulong)
0x18000b8ac  mov     ecx, [rbx+18h]
0x18000b8af  mov     r8, rdi; Size
0x18000b8b2  add     rcx, [rbx+10h]; void *
0x18000b8b6  mov     rdx, rsi; Src
0x18000b8b9  call    memcpy_0
0x18000b8be  add     [rbx+18h], edi
0x18000b8c1  mov     rbx, [rsp+68h+arg_0]
0x18000b8c6  mov     rsi, [rsp+68h+arg_8]
0x18000b8cb  add     rsp, 60h
0x18000b8cf  pop     rdi
0x18000b8d0  retn
0x18000b8d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8d8  lea     rax, WPP_GLOBAL_Control
0x18000b8df  mov     ebx, 0Dh
0x18000b8e4  cmp     rcx, rax
0x18000b8e7  jz      short loc_18000B90B
0x18000b8e9  test    byte ptr [rcx+1Ch], 1
0x18000b8ed  jz      short loc_18000B90B
0x18000b8ef  cmp     byte ptr [rcx+19h], 2
0x18000b8f3  jb      short loc_18000B90B
0x18000b8f5  mov     rcx, [rcx+10h]
0x18000b8f9  lea     edx, [rbx-2]
0x18000b8fc  mov     r9d, ebx
0x18000b8ff  lea     r8, WPP_6ed78de96a8f3b3a5d7fb4247a17f933_Traceguids
0x18000b906  call    WPP_SF_D
0x18000b90b  mov     r9d, 56h ; 'V'; int
0x18000b911  lea     r8, aAdminWmiEvents_5; "admin\\wmi\\events\\forwarding\\common"...
0x18000b918  mov     edx, ebx; unsigned int
0x18000b91a  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000b91f  call    ??0GenericException@wmi@@QEAA@KPEBDH@Z; wmi::GenericException::GenericException(ulong,char const *,int)
0x18000b924  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000b92b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000b930  call    _CxxThrowException_0
```
