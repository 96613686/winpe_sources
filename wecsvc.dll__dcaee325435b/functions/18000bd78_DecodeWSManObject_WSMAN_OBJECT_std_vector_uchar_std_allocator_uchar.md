# DecodeWSManObject(WSMAN_OBJECT *,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x18000bd78`
- end: `0x18000bf3d`
- name: `?DecodeWSManObject@@YAXPEAUWSMAN_OBJECT@@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000bbec`
- `0x18000f110`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18000bd78`
- `0x180011270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be94`
- `WsmSvc!WSManDecodeObject` at `0x18000bdba`
- `WsmSvc!WSManDecodeObject` at `0x18000be86`
- `WsmSvc!WSManDecodeObject` at `0x18000bdba`
- `WsmSvc!WSManDecodeObject` at `0x18000be86`

## string_xrefs

- `0x18000be1a`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000bedd`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
__int64 __fastcall DecodeWSManObject(__int64 a1, _QWORD *a2)
{
  __int64 v4; // r9
  DWORD LastError; // ebx
  DWORD v6; // ebx
  void **pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  char v9; // [rsp+38h] [rbp-40h]
  const char *v10; // [rsp+40h] [rbp-38h]
  __int64 v11; // [rsp+48h] [rbp-30h]
  __int64 v12; // [rsp+50h] [rbp-28h]
  DWORD v13; // [rsp+58h] [rbp-20h]
  int v14; // [rsp+5Ch] [rbp-1Ch]
  int v15; // [rsp+60h] [rbp-18h]
  unsigned int v16; // [rsp+A8h] [rbp+30h] BYREF

  a2[1] = *a2;
  std::vector<unsigned char>::resize(a2, 260);
  v4 = *a2;
  v16 = *((_DWORD *)a2 + 2) - *(_DWORD *)a2;
  if ( !(unsigned int)WSManDecodeObject(a1, 0, v16, v4, &v16) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, LastError);
      }
      v9 = 0;
      v10 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v11 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v12 = 0;
      v13 = LastError;
      v14 = -1;
      v15 = 48;
      throw (wmi::GenericException *)&pExceptionObject;
    }
    std::vector<unsigned char>::resize(a2, v16);
    if ( !(unsigned int)WSManDecodeObject(a1, 0, v16, *a2, &v16) )
    {
      v6 = GetLastError();
      if ( !v6 )
        v6 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v6);
      }
      v9 = 0;
      v10 = "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp";
      v11 = 0;
      pExceptionObject = &wmi::GenericException::`vftable';
      v12 = 0;
      v13 = v6;
      v14 = -1;
      v15 = 56;
      throw (wmi::GenericException *)&pExceptionObject;
    }
  }
  return std::vector<unsigned char>::resize(a2, v16);
}

```

## disassembly

```asm
0x18000bd78  push    rbp
0x18000bd7a  push    rbx
0x18000bd7b  push    rsi
0x18000bd7c  push    rdi
0x18000bd7d  mov     rbp, rsp
0x18000bd80  sub     rsp, 78h
0x18000bd84  mov     rax, [rdx]
0x18000bd87  mov     rdi, rdx
0x18000bd8a  mov     [rdx+8], rax
0x18000bd8e  mov     rsi, rcx
0x18000bd91  mov     edx, 104h
0x18000bd96  mov     rcx, rdi
0x18000bd99  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000bd9e  mov     r8d, [rdi+8]
0x18000bda2  lea     rax, [rbp+arg_8]
0x18000bda6  sub     r8d, [rdi]
0x18000bda9  xor     edx, edx
0x18000bdab  mov     r9, [rdi]
0x18000bdae  mov     rcx, rsi
0x18000bdb1  mov     [rbp+arg_8], r8d
0x18000bdb5  mov     [rsp+78h+var_58], rax
0x18000bdba  call    cs:__imp_WSManDecodeObject
0x18000bdc0  test    eax, eax
0x18000bdc2  jnz     loc_18000BF29
0x18000bdc8  call    cs:__imp_GetLastError
0x18000bdce  mov     ebx, eax
0x18000bdd0  cmp     eax, 7Ah ; 'z'
0x18000bdd3  jz      loc_18000BE66
0x18000bdd9  test    ebx, ebx
0x18000bddb  mov     eax, 507h
0x18000bde0  cmovz   ebx, eax
0x18000bde3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdea  lea     rax, WPP_GLOBAL_Control
0x18000bdf1  cmp     rcx, rax
0x18000bdf4  jz      short loc_18000BE1A
0x18000bdf6  test    byte ptr [rcx+1Ch], 10h
0x18000bdfa  jz      short loc_18000BE1A
0x18000bdfc  cmp     byte ptr [rcx+19h], 2
0x18000be00  jb      short loc_18000BE1A
0x18000be02  mov     rcx, [rcx+10h]
0x18000be06  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000be0d  mov     edx, 0Ah
0x18000be12  mov     r9d, ebx
0x18000be15  call    WPP_SF_D
0x18000be1a  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000be21  mov     [rbp+var_40], 0
0x18000be25  mov     [rbp+var_38], rax
0x18000be29  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000be30  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000be37  mov     [rbp+var_30], 0
0x18000be3f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000be43  mov     [rbp+pExceptionObject], rax
0x18000be47  mov     [rbp+var_28], 0
0x18000be4f  mov     [rbp+var_20], ebx
0x18000be52  mov     [rbp+var_1C], 0FFFFFFFFh
0x18000be59  mov     [rbp+var_18], 30h ; '0'
0x18000be60  call    _CxxThrowException_0
0x18000be66  mov     edx, [rbp+arg_8]
0x18000be69  mov     rcx, rdi
0x18000be6c  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000be71  mov     r9, [rdi]
0x18000be74  lea     rax, [rbp+arg_8]
0x18000be78  mov     r8d, [rbp+arg_8]
0x18000be7c  xor     edx, edx
0x18000be7e  mov     rcx, rsi
0x18000be81  mov     [rsp+78h+var_58], rax
0x18000be86  call    cs:__imp_WSManDecodeObject
0x18000be8c  test    eax, eax
0x18000be8e  jnz     loc_18000BF29
0x18000be94  call    cs:__imp_GetLastError
0x18000be9a  mov     ebx, eax
0x18000be9c  mov     eax, 507h
0x18000bea1  test    ebx, ebx
0x18000bea3  cmovz   ebx, eax
0x18000bea6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bead  lea     rax, WPP_GLOBAL_Control
0x18000beb4  cmp     rcx, rax
0x18000beb7  jz      short loc_18000BEDD
0x18000beb9  test    byte ptr [rcx+1Ch], 10h
0x18000bebd  jz      short loc_18000BEDD
0x18000bebf  cmp     byte ptr [rcx+19h], 2
0x18000bec3  jb      short loc_18000BEDD
0x18000bec5  mov     rcx, [rcx+10h]
0x18000bec9  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x18000bed0  mov     edx, 0Bh
0x18000bed5  mov     r9d, ebx
0x18000bed8  call    WPP_SF_D
0x18000bedd  lea     rax, aAdminWmiEvents_8; "admin\\wmi\\events\\forwarding\\collect"...
0x18000bee4  mov     [rbp+var_40], 0
0x18000bee8  mov     [rbp+var_38], rax
0x18000beec  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18000bef3  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18000befa  mov     [rbp+var_30], 0
0x18000bf02  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000bf06  mov     [rbp+pExceptionObject], rax
0x18000bf0a  mov     [rbp+var_28], 0
0x18000bf12  mov     [rbp+var_20], ebx
0x18000bf15  mov     [rbp+var_1C], 0FFFFFFFFh
0x18000bf1c  mov     [rbp+var_18], 38h ; '8'
0x18000bf23  call    _CxxThrowException_0
0x18000bf29  mov     edx, [rbp+arg_8]
0x18000bf2c  mov     rcx, rdi
0x18000bf2f  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18000bf34  add     rsp, 78h
0x18000bf38  pop     rdi
0x18000bf39  pop     rsi
0x18000bf3a  pop     rbx
0x18000bf3b  pop     rbp
0x18000bf3c  retn
```
