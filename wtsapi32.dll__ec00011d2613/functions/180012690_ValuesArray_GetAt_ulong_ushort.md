# ValuesArray::GetAt(ulong,ushort * *)

- ea: `0x180012690`
- end: `0x1800128c7`
- name: `?GetAt@ValuesArray@@UEAAJKPEAPEAG@Z`
- size: `567`
- prototype: `__int64 __fastcall(ValuesArray *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callees

- `0x180006734`
- `0x180007a64`
- `0x18000e2e8`
- `0x180012690`
- `0x180014ae8`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800127ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800127ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800128b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012717`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800128b2`

## string_xrefs

- `0x18001276e`: `m_spJsonArray->GetStringAt failed!`
- `0x180012871`: `StringCchCopy failed!`

## pseudocode

```c
__int64 __fastcall ValuesArray::GetAt(ValuesArray *this, __int64 a2, unsigned __int16 **a3)
{
  unsigned int v4; // ebp
  unsigned int v5; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v9; // rdx
  int v10; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v12; // rax
  __int64 v13; // rdx
  unsigned __int16 *v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+60h] [rbp+18h] BYREF
  HSTRING string; // [rsp+68h] [rbp+20h] BYREF

  string = 0;
  length = 0;
  v4 = a2;
  if ( a3 )
  {
    v7 = *((_QWORD *)this + 7);
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v7 + 64LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v8(v7, v4, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
      v12 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
      v14 = v12;
      if ( v12 )
      {
        v6 = StringCchCopyW(v12, length, StringRawBuffer);
        if ( v6 >= 0 )
        {
          *a3 = v14;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v16);
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
              ActivityIdPrefix,
              (__int64)"StringCchCopy failed!",
              v6);
          }
          operator delete(v14);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v13);
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            v15,
            (__int64)"WCHAR[]");
        }
        v6 = -2147024882;
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v9);
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        v10,
        (__int64)"m_spJsonArray->GetStringAt failed!",
        v6);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, a2);
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        v5,
        -2147024809);
    }
    v6 = -2147024809;
  }
  WindowsDeleteString(string);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012690  mov     [rsp+arg_0], rbx
0x180012695  push    rbp
0x180012696  push    rsi
0x180012697  push    rdi
0x180012698  sub     rsp, 30h
0x18001269c  mov     [rsp+48h+string], 0
0x1800126a5  mov     rsi, r8
0x1800126a8  mov     [rsp+48h+length], 0
0x1800126b0  mov     ebp, edx
0x1800126b2  test    r8, r8
0x1800126b5  jnz     short loc_18001270A
0x1800126b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126be  lea     rax, WPP_GLOBAL_Control
0x1800126c5  cmp     rcx, rax
0x1800126c8  jz      short loc_180012700
0x1800126ca  test    byte ptr [rcx+1Ch], 8
0x1800126ce  jz      short loc_180012700
0x1800126d0  cmp     byte ptr [rcx+19h], 2
0x1800126d4  jb      short loc_180012700
0x1800126d6  call    RdpX_GetActivityIdPrefix
0x1800126db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126e2  lea     edx, [rsi+0Dh]
0x1800126e5  mov     r9d, eax
0x1800126e8  mov     dword ptr [rsp+48h+var_28], 80070057h
0x1800126f0  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800126f7  mov     rcx, [rcx+10h]
0x1800126fb  call    WPP_SF_DD
0x180012700  mov     ebx, 80070057h
0x180012705  jmp     loc_1800128AD
0x18001270a  mov     rdi, [rcx+38h]
0x18001270e  xor     ecx, ecx; string
0x180012710  mov     rax, [rdi]
0x180012713  mov     rbx, [rax+40h]
0x180012717  call    cs:__imp_WindowsDeleteString
0x18001271d  lea     r8, [rsp+48h+string]
0x180012722  mov     [rsp+48h+string], 0
0x18001272b  mov     edx, ebp
0x18001272d  mov     rcx, rdi
0x180012730  mov     rax, rbx
0x180012733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012738  mov     ebx, eax
0x18001273a  test    eax, eax
0x18001273c  jns     short loc_1800127A2
0x18001273e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012745  lea     rax, WPP_GLOBAL_Control
0x18001274c  cmp     rcx, rax
0x18001274f  jz      loc_1800128AD
0x180012755  test    byte ptr [rcx+1Ch], 8
0x180012759  jz      loc_1800128AD
0x18001275f  cmp     byte ptr [rcx+19h], 2
0x180012763  jb      loc_1800128AD
0x180012769  call    RdpX_GetActivityIdPrefix
0x18001276e  lea     rcx, aMSpjsonarrayGe; "m_spJsonArray->GetStringAt failed!"
0x180012775  mov     [rsp+48h+var_20], ebx
0x180012779  mov     [rsp+48h+var_28], rcx
0x18001277e  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012785  mov     rcx, cs:WPP_GLOBAL_Control
0x18001278c  mov     edx, 0Eh
0x180012791  mov     r9d, eax
0x180012794  mov     rcx, [rcx+10h]
0x180012798  call    WPP_SF_DsD
0x18001279d  jmp     loc_1800128AD
0x1800127a2  mov     rcx, [rsp+48h+string]; string
0x1800127a7  lea     rdx, [rsp+48h+length]; length
0x1800127ac  call    cs:__imp_WindowsGetStringRawBuffer
0x1800127b2  mov     ecx, [rsp+48h+length]
0x1800127b6  mov     rbx, rax
0x1800127b9  inc     ecx
0x1800127bb  mov     eax, 2
0x1800127c0  mov     edx, ecx
0x1800127c2  mov     [rsp+48h+length], ecx
0x1800127c6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800127cd  mul     rdx
0x1800127d0  cmovb   rax, rcx
0x1800127d4  mov     rcx, rax; Size
0x1800127d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800127dc  mov     rdi, rax
0x1800127df  test    rax, rax
0x1800127e2  jnz     short loc_180012838
0x1800127e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800127eb  lea     rax, WPP_GLOBAL_Control
0x1800127f2  cmp     rcx, rax
0x1800127f5  jz      short loc_180012831
0x1800127f7  test    byte ptr [rcx+1Ch], 8
0x1800127fb  jz      short loc_180012831
0x1800127fd  cmp     byte ptr [rcx+19h], 2
0x180012801  jb      short loc_180012831
0x180012803  call    RdpX_GetActivityIdPrefix
0x180012808  lea     rcx, aWchar; "WCHAR[]"
0x18001280f  mov     r9d, eax
0x180012812  mov     [rsp+48h+var_28], rcx
0x180012817  lea     edx, [rdi+0Fh]
0x18001281a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012821  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012828  mov     rcx, [rcx+10h]
0x18001282c  call    WPP_SF_Ds
0x180012831  mov     ebx, 8007000Eh
0x180012836  jmp     short loc_1800128AD
0x180012838  mov     edx, [rsp+48h+length]; unsigned __int64
0x18001283c  mov     r8, rbx; unsigned __int16 *
0x18001283f  mov     rcx, rdi; unsigned __int16 *
0x180012842  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012847  mov     ebx, eax
0x180012849  test    eax, eax
0x18001284b  jns     short loc_1800128AA
0x18001284d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012854  lea     rax, WPP_GLOBAL_Control
0x18001285b  cmp     rcx, rax
0x18001285e  jz      short loc_1800128A0
0x180012860  test    byte ptr [rcx+1Ch], 8
0x180012864  jz      short loc_1800128A0
0x180012866  cmp     byte ptr [rcx+19h], 2
0x18001286a  jb      short loc_1800128A0
0x18001286c  call    RdpX_GetActivityIdPrefix
0x180012871  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x180012878  mov     [rsp+48h+var_20], ebx
0x18001287c  mov     [rsp+48h+var_28], rcx
0x180012881  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012888  mov     rcx, cs:WPP_GLOBAL_Control
0x18001288f  mov     edx, 10h
0x180012894  mov     r9d, eax
0x180012897  mov     rcx, [rcx+10h]
0x18001289b  call    WPP_SF_DsD
0x1800128a0  mov     rcx, rdi; Block
0x1800128a3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800128a8  jmp     short loc_1800128AD
0x1800128aa  mov     [rsi], rdi
0x1800128ad  mov     rcx, [rsp+48h+string]; string
0x1800128b2  call    cs:__imp_WindowsDeleteString
0x1800128b8  mov     eax, ebx
0x1800128ba  mov     rbx, [rsp+48h+arg_0]
0x1800128bf  add     rsp, 30h
0x1800128c3  pop     rdi
0x1800128c4  pop     rsi
0x1800128c5  pop     rbp
0x1800128c6  retn
```
