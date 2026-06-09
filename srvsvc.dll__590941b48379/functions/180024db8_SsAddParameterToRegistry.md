# SsAddParameterToRegistry

- ea: `0x180024db8`
- end: `0x180024f25`
- name: `SsAddParameterToRegistry`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012734`

## callees

- `0x180020de8`
- `0x180024db8`
- `0x180026220`
- `0x1800268d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024ecd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180024ecd`
- `ntdll!RtlWriteRegistryValue` at `0x180024e7a`
- `ntdll!RtlWriteRegistryValue` at `0x180024e7a`

## string_xrefs

- `0x180024ec3`: `srvcomment`

## pseudocode

```c
__int64 __fastcall SsAddParameterToRegistry(__int64 a1, BYTE **a2)
{
  __int64 v2; // r9
  __int64 result; // rax
  BYTE *ValueData; // rcx
  ULONG v7; // r9d
  __int64 v8; // rax
  ULONG ValueLength; // eax
  const WCHAR *v10; // rbp
  NTSTATUS v11; // eax

  v2 = *(unsigned int *)(a1 + 8);
  if ( !(_DWORD)v2 || (result = (unsigned int)(v2 - 1), (_DWORD)v2 == 1) )
  {
    v7 = 4;
    ValueData = (BYTE *)a2;
    ValueLength = 4;
  }
  else
  {
    if ( (_DWORD)v2 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids, v2);
      }
      return result;
    }
    ValueData = *a2;
    v7 = 1;
    if ( *a2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&ValueData[2 * v8] );
      ValueLength = 2 * v8 + 2;
    }
    else
    {
      ValueLength = 0;
    }
  }
  v10 = *(const WCHAR **)a1;
  v11 = RtlWriteRegistryValue(1u, L"LanmanServer\\Parameters", v10, v7, ValueData, ValueLength);
  if ( v11 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
      v11,
      (__int64)v10);
  }
  result = _o__wcsicmp(v10, L"srvcomment");
  if ( !(_DWORD)result )
  {
    result = SsSaveSrvComment(*a2);
    if ( (int)result < 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      return WPP_SF_dS(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               12,
               (unsigned int)WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids,
               result,
               (__int64)v10);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024db8  push    rbp
0x180024dba  push    rsi
0x180024dbb  push    rdi
0x180024dbc  push    r14
0x180024dbe  sub     rsp, 38h
0x180024dc2  mov     r9d, [rcx+8]
0x180024dc6  xor     r14d, r14d
0x180024dc9  mov     rsi, rdx
0x180024dcc  mov     rbp, rcx
0x180024dcf  mov     eax, r9d
0x180024dd2  test    r9d, r9d
0x180024dd5  jz      short loc_180024E52
0x180024dd7  sub     eax, 1
0x180024dda  jz      short loc_180024E52
0x180024ddc  cmp     eax, 1
0x180024ddf  jz      short loc_180024E28
0x180024de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180024de8  lea     rdi, WPP_GLOBAL_Control
0x180024def  cmp     rcx, rdi
0x180024df2  jz      loc_180024F1B
0x180024df8  test    dword ptr [rcx+1Ch], 100h
0x180024dff  jz      loc_180024F1B
0x180024e05  cmp     byte ptr [rcx+19h], 1
0x180024e09  jb      loc_180024F1B
0x180024e0f  mov     rcx, [rcx+10h]
0x180024e13  lea     edx, [r14+0Ah]
0x180024e17  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180024e1e  call    WPP_SF_d
0x180024e23  jmp     loc_180024F1B
0x180024e28  mov     rcx, [rdx]
0x180024e2b  mov     r9d, 1
0x180024e31  test    rcx, rcx
0x180024e34  jz      short loc_180024E4D
0x180024e36  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024e3a  inc     rax
0x180024e3d  cmp     [rcx+rax*2], r14w
0x180024e42  jnz     short loc_180024E3A
0x180024e44  lea     eax, ds:2[rax*2]
0x180024e4b  jmp     short loc_180024E5E
0x180024e4d  mov     eax, r14d
0x180024e50  jmp     short loc_180024E5E
0x180024e52  mov     r9d, 4; ValueType
0x180024e58  mov     rcx, rsi
0x180024e5b  mov     eax, r9d
0x180024e5e  mov     rbp, [rbp+0]
0x180024e62  lea     rdx, aLanmanserverPa; "LanmanServer\\Parameters"
0x180024e69  mov     [rsp+58h+ValueLength], eax; ValueLength
0x180024e6d  mov     r8, rbp; ValueName
0x180024e70  mov     [rsp+58h+ValueData], rcx; ValueData
0x180024e75  mov     ecx, 1; RelativeTo
0x180024e7a  call    cs:__imp_RtlWriteRegistryValue
0x180024e80  lea     rdi, WPP_GLOBAL_Control
0x180024e87  test    eax, eax
0x180024e89  jns     short loc_180024EC3
0x180024e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024e92  cmp     rcx, rdi
0x180024e95  jz      short loc_180024EC3
0x180024e97  test    dword ptr [rcx+1Ch], 100h
0x180024e9e  jz      short loc_180024EC3
0x180024ea0  cmp     byte ptr [rcx+19h], 1
0x180024ea4  jb      short loc_180024EC3
0x180024ea6  mov     rcx, [rcx+10h]
0x180024eaa  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180024eb1  mov     edx, 0Bh
0x180024eb6  mov     [rsp+58h+ValueData], rbp
0x180024ebb  mov     r9d, eax
0x180024ebe  call    WPP_SF_dS
0x180024ec3  lea     rdx, aSrvcomment; "srvcomment"
0x180024eca  mov     rcx, rbp
0x180024ecd  call    cs:__imp__o__wcsicmp
0x180024ed3  test    eax, eax
0x180024ed5  jnz     short loc_180024F1B
0x180024ed7  mov     rcx, [rsi]; lpData
0x180024eda  call    SsSaveSrvComment
0x180024edf  test    eax, eax
0x180024ee1  jns     short loc_180024F1B
0x180024ee3  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eea  cmp     rcx, rdi
0x180024eed  jz      short loc_180024F1B
0x180024eef  test    dword ptr [rcx+1Ch], 100h
0x180024ef6  jz      short loc_180024F1B
0x180024ef8  cmp     byte ptr [rcx+19h], 1
0x180024efc  jb      short loc_180024F1B
0x180024efe  mov     rcx, [rcx+10h]
0x180024f02  lea     r8, WPP_6c51fa01af1134468f88fcdefbc326dc_Traceguids
0x180024f09  mov     edx, 0Ch
0x180024f0e  mov     [rsp+58h+ValueData], rbp
0x180024f13  mov     r9d, eax
0x180024f16  call    WPP_SF_dS
0x180024f1b  add     rsp, 38h
0x180024f1f  pop     r14
0x180024f21  pop     rdi
0x180024f22  pop     rsi
0x180024f23  pop     rbp
0x180024f24  retn
```
