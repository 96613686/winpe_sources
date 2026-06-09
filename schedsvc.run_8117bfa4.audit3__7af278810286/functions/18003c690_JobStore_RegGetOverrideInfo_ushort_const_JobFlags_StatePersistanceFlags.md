# JobStore::RegGetOverrideInfo(ushort const *,JobFlags::StatePersistanceFlags *)

- ea: `0x18003c690`
- end: `0x18003c87d`
- name: `?RegGetOverrideInfo@JobStore@@QEBAXPEBGPEAW4StatePersistanceFlags@JobFlags@@@Z`
- size: `493`
- prototype: `void(JobStore *__hidden this, const unsigned __int16 *, enum JobFlags::StatePersistanceFlags *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180047ee0`
- `0x18006fed4`

## callees

- `0x18003c690`
- `0x1800529a0`
- `0x180056714`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003c795`
- `OLEAUT32!__imp_SysAllocString` at `0x18003c795`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c74a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c786`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c74a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003c786`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c710`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c710`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c7f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003c7f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c761`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c761`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall JobStore::RegGetOverrideInfo(
        HKEY *this,
        const unsigned __int16 *a2,
        enum JobFlags::StatePersistanceFlags *a3)
{
  BSTR v6; // rbx
  __int64 v7; // rax
  LSTATUS v8; // eax
  char v9; // r8
  LSTATUS v10; // eax
  HKEY hKey[7]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+8h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF

  Type = 0;
  cbData = 0;
  Data = 0;
  hKey[0] = 0;
  v6 = 0;
  *(_DWORD *)a3 = 0;
  if ( this[4] )
  {
    if ( a2 )
    {
      SysFreeString(0);
      v6 = SysAllocString(a2);
      hKey[1] = (HKEY)v6;
      if ( !v6 )
        ATL::PrivateAtlThrow(0x8007000E);
    }
    LODWORD(v7) = 0;
    if ( *v6 )
    {
      do
      {
        if ( v6[(unsigned int)v7] == 92 )
          v6[(unsigned int)v7] = 47;
        v7 = (unsigned int)(v7 + 1);
      }
      while ( v6[v7] );
    }
    v8 = RegOpenKeyExW(this[4], v6, 0, 0xF003Fu, hKey);
    v9 = v8;
    if ( !v8 )
    {
      cbData = 4;
      v10 = RegQueryValueExW(hKey[0], L"StateFlags", 0, &Type, (LPBYTE)&Data, &cbData);
      v9 = v10;
      if ( !v10 && Type == 4 && cbData == 4 && (Data | 3) == 3 )
        *(_DWORD *)a3 = Data;
    }
  }
  else
  {
    v9 = 50;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_SSD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      88,
      (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids,
      (_DWORD)a2,
      (__int64)a2,
      v9);
  }
  SysFreeString(v6);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
}

```

## disassembly

```asm
0x18003c690  mov     rax, rsp
0x18003c693  push    rbx
0x18003c694  push    rbp
0x18003c695  push    rsi
0x18003c696  push    rdi
0x18003c697  push    r14
0x18003c699  sub     rsp, 40h
0x18003c69d  mov     r14, r8
0x18003c6a0  mov     rsi, rdx
0x18003c6a3  mov     rdi, rcx
0x18003c6a6  xor     ebp, ebp
0x18003c6a8  mov     [rax+18h], ebp
0x18003c6ab  mov     [rax+8], ebp
0x18003c6ae  mov     [rax+20h], ebp
0x18003c6b1  mov     [rax-38h], rbp
0x18003c6b5  mov     ebx, ebp
0x18003c6b7  mov     [r8], ebp
0x18003c6ba  cmp     [rcx+20h], rbp
0x18003c6be  jz      loc_18003C840
0x18003c6c4  test    rdx, rdx
0x18003c6c7  jnz     loc_18003C784
0x18003c6cd  mov     eax, ebp
0x18003c6cf  cmp     [rbx], ax
0x18003c6d2  jz      short loc_18003C6F6
0x18003c6d4  nop     dword ptr [rax+00h]
0x18003c6d8  nop     dword ptr [rax+rax+00000000h]
0x18003c6e0  mov     ecx, eax
0x18003c6e2  cmp     word ptr [rbx+rcx*2], 5Ch ; '\'
0x18003c6e7  jz      loc_18003C779
0x18003c6ed  inc     eax
0x18003c6ef  cmp     word ptr [rbx+rax*2], 0
0x18003c6f4  jnz     short loc_18003C6E0
0x18003c6f6  lea     rax, [rsp+68h+hKey]
0x18003c6fb  mov     [rsp+68h+phkResult], rax; phkResult
0x18003c700  mov     r9d, 0F003Fh; samDesired
0x18003c706  xor     r8d, r8d; ulOptions
0x18003c709  mov     rdx, rbx; lpSubKey
0x18003c70c  mov     rcx, [rdi+20h]; hKey
0x18003c710  call    cs:__imp_RegOpenKeyExW
0x18003c717  nop     dword ptr [rax+rax+00h]
0x18003c71c  mov     r8d, eax
0x18003c71f  test    eax, eax
0x18003c721  jz      loc_18003C7BD
0x18003c727  lea     rax, WPP_GLOBAL_Control
0x18003c72e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c735  cmp     rcx, rax
0x18003c738  jz      short loc_18003C747
0x18003c73a  test    dword ptr [rcx+1Ch], 40000h
0x18003c741  jnz     loc_18003C84B
0x18003c747  mov     rcx, rbx; bstrString
0x18003c74a  call    cs:__imp_SysFreeString
0x18003c751  nop     dword ptr [rax+rax+00h]
0x18003c756  nop
0x18003c757  mov     rcx, [rsp+68h+hKey]; hKey
0x18003c75c  test    rcx, rcx
0x18003c75f  jz      short loc_18003C76D
0x18003c761  call    cs:__imp_RegCloseKey
0x18003c768  nop     dword ptr [rax+rax+00h]
0x18003c76d  add     rsp, 40h
0x18003c771  pop     r14
0x18003c773  pop     rdi
0x18003c774  pop     rsi
0x18003c775  pop     rbp
0x18003c776  pop     rbx
0x18003c777  retn
0x18003c779  mov     word ptr [rbx+rcx*2], 2Fh ; '/'
0x18003c77f  jmp     loc_18003C6ED
0x18003c784  xor     ecx, ecx; bstrString
0x18003c786  call    cs:__imp_SysFreeString
0x18003c78d  nop     dword ptr [rax+rax+00h]
0x18003c792  mov     rcx, rsi; psz
0x18003c795  call    cs:__imp_SysAllocString
0x18003c79c  nop     dword ptr [rax+rax+00h]
0x18003c7a1  mov     rbx, rax
0x18003c7a4  mov     [rsp+68h+var_30], rax
0x18003c7a9  test    rax, rax
0x18003c7ac  jnz     loc_18003C6CD
0x18003c7b2  mov     ecx, 8007000Eh; unsigned int
0x18003c7b7  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18003c7bd  mov     [rsp+68h+cbData], 4
0x18003c7c5  lea     rax, [rsp+68h+cbData]
0x18003c7ca  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18003c7cf  lea     rax, [rsp+68h+Data]
0x18003c7d7  mov     [rsp+68h+phkResult], rax; lpData
0x18003c7dc  lea     r9, [rsp+68h+Type]; lpType
0x18003c7e4  xor     r8d, r8d; lpReserved
0x18003c7e7  lea     rdx, aStateflags; "StateFlags"
0x18003c7ee  mov     rcx, [rsp+68h+hKey]; hKey
0x18003c7f3  call    cs:__imp_RegQueryValueExW
0x18003c7fa  nop     dword ptr [rax+rax+00h]
0x18003c7ff  mov     r8d, eax
0x18003c802  test    eax, eax
0x18003c804  jnz     loc_18003C727
0x18003c80a  cmp     [rsp+68h+Type], 4
0x18003c812  jnz     loc_18003C727
0x18003c818  cmp     [rsp+68h+cbData], 4
0x18003c81d  jnz     loc_18003C727
0x18003c823  mov     ecx, [rsp+68h+Data]
0x18003c82a  mov     eax, ecx
0x18003c82c  or      eax, 3
0x18003c82f  cmp     eax, 3
0x18003c832  jnz     loc_18003C727
0x18003c838  mov     [r14], ecx
0x18003c83b  jmp     loc_18003C727
0x18003c840  mov     r8d, 32h ; '2'
0x18003c846  jmp     loc_18003C727
0x18003c84b  cmp     byte ptr [rcx+19h], 2
0x18003c84f  jb      loc_18003C747
0x18003c855  mov     edx, 58h ; 'X'
0x18003c85a  mov     dword ptr [rsp+68h+lpcbData], r8d
0x18003c85f  mov     [rsp+68h+phkResult], rsi
0x18003c864  mov     r9, rsi
0x18003c867  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x18003c86e  mov     rcx, [rcx+10h]
0x18003c872  call    WPP_SF_SSD
0x18003c877  jmp     loc_18003C747
```
