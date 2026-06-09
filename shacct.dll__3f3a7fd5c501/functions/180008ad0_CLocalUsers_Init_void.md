# CLocalUsers::_Init(void)

- ea: `0x180008ad0`
- end: `0x180008bc0`
- name: `?_Init@CLocalUsers@@MEAAJXZ`
- size: `240`
- prototype: `__int64 __fastcall(CLocalUsers *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800037e0`
- `0x180003c30`
- `0x180008ad0`
- `0x18000b9e0`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008b48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008bab`

## pseudocode

```c
__int64 __fastcall CLocalUsers::_Init(CLocalUsers *this)
{
  int v1; // edi
  void *v3; // rsi
  int v4; // eax
  __int64 result; // rax
  void *v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  pv = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v1 = CSGetAccountDomainSid(&pv);
    if ( v1 >= 0 )
    {
      v3 = pv;
      v4 = CSGetUserRIDEnumeration(pv, (__int64)this + 32, (__int64)this + 24);
      v1 = v4;
      if ( v4 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
          (unsigned int)v4);
      }
      CoTaskMemFree(v3);
    }
  }
  if ( *((_QWORD *)this + 2) )
    return (unsigned int)v1;
  result = CSGetBuiltInDomainSid(&pv);
  if ( (int)result >= 0 )
  {
    v6 = pv;
    v7 = CSGetUserRIDEnumeration(pv, (__int64)this + 16, (__int64)this + 12);
    v8 = v7;
    if ( v7 < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
        (unsigned int)v7);
    }
    CoTaskMemFree(v6);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180008ad0  push    rbx
0x180008ad2  push    rbp
0x180008ad3  push    rsi
0x180008ad4  push    rdi
0x180008ad5  sub     rsp, 28h
0x180008ad9  xor     edi, edi
0x180008adb  lea     rbp, WPP_GLOBAL_Control
0x180008ae2  mov     rbx, rcx
0x180008ae5  mov     [rsp+48h+pv], rdi
0x180008aea  cmp     [rcx+20h], rdi
0x180008aee  jnz     short loc_180008B4E
0x180008af0  lea     rcx, [rsp+48h+pv]
0x180008af5  call    CSGetAccountDomainSid
0x180008afa  mov     edi, eax
0x180008afc  test    eax, eax
0x180008afe  js      short loc_180008B4E
0x180008b00  mov     rsi, [rsp+48h+pv]
0x180008b05  lea     r8, [rbx+18h]
0x180008b09  mov     rcx, rsi
0x180008b0c  lea     rdx, [rbx+20h]
0x180008b10  call    CSGetUserRIDEnumeration
0x180008b15  mov     edi, eax
0x180008b17  test    eax, eax
0x180008b19  jns     short loc_180008B45
0x180008b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b22  cmp     rcx, rbp
0x180008b25  jz      short loc_180008B45
0x180008b27  test    byte ptr [rcx+1Ch], 2
0x180008b2b  jz      short loc_180008B45
0x180008b2d  mov     rcx, [rcx+10h]
0x180008b31  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180008b38  mov     edx, 18h
0x180008b3d  mov     r9d, eax
0x180008b40  call    WPP_SF_d
0x180008b45  mov     rcx, rsi; pv
0x180008b48  call    cs:__imp_CoTaskMemFree
0x180008b4e  cmp     qword ptr [rbx+10h], 0
0x180008b53  jnz     short loc_180008BB5
0x180008b55  lea     rcx, [rsp+48h+pv]
0x180008b5a  call    CSGetBuiltInDomainSid
0x180008b5f  test    eax, eax
0x180008b61  js      short loc_180008BB7
0x180008b63  mov     rdi, [rsp+48h+pv]
0x180008b68  lea     r8, [rbx+0Ch]
0x180008b6c  mov     rcx, rdi
0x180008b6f  lea     rdx, [rbx+10h]
0x180008b73  call    CSGetUserRIDEnumeration
0x180008b78  mov     ebx, eax
0x180008b7a  test    eax, eax
0x180008b7c  jns     short loc_180008BA8
0x180008b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b85  cmp     rcx, rbp
0x180008b88  jz      short loc_180008BA8
0x180008b8a  test    byte ptr [rcx+1Ch], 2
0x180008b8e  jz      short loc_180008BA8
0x180008b90  mov     rcx, [rcx+10h]
0x180008b94  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x180008b9b  mov     edx, 19h
0x180008ba0  mov     r9d, eax
0x180008ba3  call    WPP_SF_d
0x180008ba8  mov     rcx, rdi; pv
0x180008bab  call    cs:__imp_CoTaskMemFree
0x180008bb1  mov     eax, ebx
0x180008bb3  jmp     short loc_180008BB7
0x180008bb5  mov     eax, edi
0x180008bb7  add     rsp, 28h
0x180008bbb  pop     rdi
0x180008bbc  pop     rsi
0x180008bbd  pop     rbp
0x180008bbe  pop     rbx
0x180008bbf  retn
```
