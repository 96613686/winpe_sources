# SystemTimeToString(_SYSTEMTIME const &,ushort *,ulong,_FILETIME const *)

- ea: `0x18001fb3c`
- end: `0x18001fd16`
- name: `?SystemTimeToString@@YAPEAGAEBU_SYSTEMTIME@@PEAGKPEBU_FILETIME@@@Z`
- size: `474`
- prototype: `unsigned __int16 *__fastcall(const struct _SYSTEMTIME *, unsigned __int16 *, __int64, const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800165c0`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x18001fb3c`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18001fb9d`
- `msvcrt!swprintf_s` at `0x18001fc65`
- `msvcrt!swprintf_s` at `0x18001fc7d`
- `msvcrt!swprintf_s` at `0x18001fb9d`
- `msvcrt!swprintf_s` at `0x18001fc65`
- `msvcrt!swprintf_s` at `0x18001fc7d`

## string_xrefs

- `0x18001fbe8`: `admin\wmi\events\forwarding\common\timehelp.cpp`
- `0x18001fcc2`: `admin\wmi\events\forwarding\common\timehelp.cpp`

## pseudocode

```c
unsigned __int16 *__fastcall SystemTimeToString(
        const struct _SYSTEMTIME *a1,
        unsigned __int16 *a2,
        __int64 a3,
        const struct _FILETIME *a4)
{
  unsigned int wMilliseconds; // r14d
  int v7; // eax
  wchar_t *v8; // r10
  size_t v9; // rcx
  int v10; // eax
  void **pExceptionObject; // [rsp+50h] [rbp-9h] BYREF
  char v13; // [rsp+58h] [rbp-1h]
  const char *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  __int64 v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+78h] [rbp+1Fh]
  int v18; // [rsp+7Ch] [rbp+23h]
  int v19; // [rsp+80h] [rbp+27h]

  wMilliseconds = a1->wMilliseconds;
  v7 = swprintf_s(
         a2,
         0x20u,
         L"%4.4hd-%2.2hd-%2.2hdT%2.2hd:%2.2hd:%2.2hd",
         a1->wYear,
         a1->wMonth,
         a1->wDay,
         a1->wHour,
         a1->wMinute,
         a1->wSecond);
  if ( v7 == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_610b8bfd60293761ca8071fb3cb577e0_Traceguids, 13);
    }
    v17 = 13;
    v13 = 0;
    v14 = "admin\\wmi\\events\\forwarding\\common\\timehelp.cpp";
    v15 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v16 = 0;
    v18 = -1;
    v19 = 37;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  v8 = &a2[v7];
  v9 = (unsigned int)(32 - v7);
  if ( a4 )
    v10 = swprintf_s(v8, (unsigned int)v9, L".%09I64uZ", 100 * (*(_QWORD *)a4 % 0x989680uLL));
  else
    v10 = swprintf_s(v8, v9, L".%03huZ", wMilliseconds);
  if ( v10 == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_610b8bfd60293761ca8071fb3cb577e0_Traceguids, 13);
    }
    v13 = 0;
    v14 = "admin\\wmi\\events\\forwarding\\common\\timehelp.cpp";
    v15 = 0;
    pExceptionObject = &wmi::GenericException::`vftable';
    v16 = 0;
    v17 = 13;
    v18 = -1;
    v19 = 56;
    throw (wmi::GenericException *)&pExceptionObject;
  }
  return a2;
}

```

## disassembly

```asm
0x18001fb3c  push    rbp
0x18001fb3e  push    rbx
0x18001fb3f  push    rsi
0x18001fb40  push    rdi
0x18001fb41  push    r14
0x18001fb43  lea     rbp, [rsp-37h]
0x18001fb48  sub     rsp, 90h
0x18001fb4f  movzx   r8d, word ptr [rcx+0Ah]
0x18001fb54  mov     rdi, rdx
0x18001fb57  movzx   ebx, word ptr [rcx+2]
0x18001fb5b  mov     rsi, r9
0x18001fb5e  movzx   eax, word ptr [rcx+0Ch]
0x18001fb62  movzx   r10d, word ptr [rcx+8]
0x18001fb67  movzx   r11d, word ptr [rcx+6]
0x18001fb6c  movzx   r14d, word ptr [rcx+0Eh]
0x18001fb71  movzx   r9d, word ptr [rcx]
0x18001fb75  mov     rcx, rdi; Buffer
0x18001fb78  mov     [rsp+0B0h+var_70], eax
0x18001fb7c  mov     [rsp+0B0h+var_78], r8d
0x18001fb81  lea     r8, a44hd22hd22hdt2; "%4.4hd-%2.2hd-%2.2hdT%2.2hd:%2.2hd:%2.2"...
0x18001fb88  mov     [rsp+0B0h+var_80], r10d
0x18001fb8d  mov     [rsp+0B0h+var_88], r11d
0x18001fb92  mov     [rsp+0B0h+var_90], ebx
0x18001fb96  mov     ebx, 20h ; ' '
0x18001fb9b  mov     edx, ebx; BufferCount
0x18001fb9d  call    cs:__imp_swprintf_s
0x18001fba3  movsxd  rcx, eax
0x18001fba6  cmp     ecx, 0FFFFFFFFh
0x18001fba9  jnz     short loc_18001FC28
0x18001fbab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbb2  lea     rax, WPP_GLOBAL_Control
0x18001fbb9  lea     edi, [rbx-13h]
0x18001fbbc  cmp     rcx, rax
0x18001fbbf  jz      short loc_18001FBE3
0x18001fbc1  test    byte ptr [rcx+1Ch], 1
0x18001fbc5  jz      short loc_18001FBE3
0x18001fbc7  cmp     byte ptr [rcx+19h], 2
0x18001fbcb  jb      short loc_18001FBE3
0x18001fbcd  mov     rcx, [rcx+10h]
0x18001fbd1  lea     edx, [rbx-16h]
0x18001fbd4  mov     r9d, edi
0x18001fbd7  lea     r8, WPP_610b8bfd60293761ca8071fb3cb577e0_Traceguids
0x18001fbde  call    WPP_SF_D
0x18001fbe3  xor     ebx, ebx
0x18001fbe5  mov     [rbp+57h+var_38], edi
0x18001fbe8  lea     rax, aAdminWmiEvents_2; "admin\\wmi\\events\\forwarding\\common"...
0x18001fbef  mov     [rbp+57h+var_58], bl
0x18001fbf2  mov     [rbp+57h+var_50], rax
0x18001fbf6  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001fbfd  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001fc04  mov     [rbp+57h+var_48], rbx
0x18001fc08  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001fc0c  mov     [rbp+57h+pExceptionObject], rax
0x18001fc10  mov     [rbp+57h+var_40], rbx
0x18001fc14  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001fc1b  mov     [rbp+57h+var_30], 25h ; '%'
0x18001fc22  call    _CxxThrowException_0
0x18001fc28  sub     ebx, ecx
0x18001fc2a  lea     r10, [rdi+rcx*2]
0x18001fc2e  mov     ecx, ebx
0x18001fc30  xor     ebx, ebx
0x18001fc32  test    rsi, rsi
0x18001fc35  jz      short loc_18001FC6D
0x18001fc37  mov     r8, [rsi]
0x18001fc3a  mov     rax, 0D6BF94D5E57A42BDh
0x18001fc44  mul     r8
0x18001fc47  shr     rdx, 17h
0x18001fc4b  imul    rax, rdx, 989680h
0x18001fc52  mov     edx, ecx; BufferCount
0x18001fc54  mov     rcx, r10; Buffer
0x18001fc57  sub     r8, rax
0x18001fc5a  imul    r9, r8, 64h ; 'd'
0x18001fc5e  lea     r8, a09i64uz; ".%09I64uZ"
0x18001fc65  call    cs:__imp_swprintf_s
0x18001fc6b  jmp     short loc_18001FC83
0x18001fc6d  mov     rdx, rcx; BufferCount
0x18001fc70  lea     r8, a03huz; ".%03huZ"
0x18001fc77  mov     rcx, r10; Buffer
0x18001fc7a  mov     r9d, r14d
0x18001fc7d  call    cs:__imp_swprintf_s
0x18001fc83  cmp     eax, 0FFFFFFFFh
0x18001fc86  jnz     short loc_18001FD05
0x18001fc88  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc8f  lea     rax, WPP_GLOBAL_Control
0x18001fc96  mov     edi, 0Dh
0x18001fc9b  cmp     rcx, rax
0x18001fc9e  jz      short loc_18001FCC2
0x18001fca0  test    byte ptr [rcx+1Ch], 1
0x18001fca4  jz      short loc_18001FCC2
0x18001fca6  cmp     byte ptr [rcx+19h], 2
0x18001fcaa  jb      short loc_18001FCC2
0x18001fcac  mov     rcx, [rcx+10h]
0x18001fcb0  lea     edx, [rdi-2]
0x18001fcb3  mov     r9d, edi
0x18001fcb6  lea     r8, WPP_610b8bfd60293761ca8071fb3cb577e0_Traceguids
0x18001fcbd  call    WPP_SF_D
0x18001fcc2  lea     rax, aAdminWmiEvents_2; "admin\\wmi\\events\\forwarding\\common"...
0x18001fcc9  mov     [rbp+57h+var_58], bl
0x18001fccc  mov     [rbp+57h+var_50], rax
0x18001fcd0  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001fcd7  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001fcde  mov     [rbp+57h+var_48], rbx
0x18001fce2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001fce6  mov     [rbp+57h+pExceptionObject], rax
0x18001fcea  mov     [rbp+57h+var_40], rbx
0x18001fcee  mov     [rbp+57h+var_38], edi
0x18001fcf1  mov     [rbp+57h+var_34], 0FFFFFFFFh
0x18001fcf8  mov     [rbp+57h+var_30], 38h ; '8'
0x18001fcff  call    _CxxThrowException_0
0x18001fd05  mov     rax, rdi
0x18001fd08  add     rsp, 90h
0x18001fd0f  pop     r14
0x18001fd11  pop     rdi
0x18001fd12  pop     rsi
0x18001fd13  pop     rbx
0x18001fd14  pop     rbp
0x18001fd15  retn
```
