# HrSetErrorInfo(ushort const *,_GUID const &)

- ea: `0x18003b0bc`
- end: `0x18003b1c3`
- name: `?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180037620`
- `0x180037aa0`
- `0x18004f5b0`
- `0x18004ff50`

## callees

- `0x180014038`
- `0x18003b0bc`
- `0x180049258`
- `0x180059010`

## import_xrefs

- `combase!CreateErrorInfo` at `0x18003b0e6`
- `combase!CreateErrorInfo` at `0x18003b0e6`
- `combase!SetErrorInfo` at `0x18003b155`
- `combase!SetErrorInfo` at `0x18003b155`

## pseudocode

```c
__int64 __fastcall HrSetErrorInfo(const unsigned __int16 *a1, const struct _GUID *a2)
{
  HRESULT ErrorInfo; // ebx
  struct IUnknown *v6; // [rsp+50h] [rbp+18h] BYREF
  IErrorInfo *perrinfo; // [rsp+58h] [rbp+20h] BYREF

  perrinfo = 0;
  v6 = 0;
  ErrorInfo = CreateErrorInfo((ICreateErrorInfo **)&v6);
  if ( ErrorInfo >= 0 )
  {
    ErrorInfo = ((__int64 (__fastcall *)(struct IUnknown *, const unsigned __int16 *))v6->lpVtbl[1].Release)(v6, a1);
    if ( ErrorInfo >= 0 )
    {
      ErrorInfo = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *))v6->lpVtbl[1].QueryInterface)(
                    v6,
                    a2);
      if ( ErrorInfo >= 0 )
      {
        ErrorInfo = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IErrorInfo **))v6->lpVtbl->QueryInterface)(
                      v6,
                      &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
                      &perrinfo);
        if ( ErrorInfo >= 0 )
          ErrorInfo = SetErrorInfo(0, perrinfo);
      }
    }
  }
  ReleaseObj((struct IUnknown *)perrinfo);
  ReleaseObj(v6);
  if ( ErrorInfo && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids,
      (_DWORD)a1,
      ErrorInfo);
  return (unsigned int)ErrorInfo;
}

```

## disassembly

```asm
0x18003b0bc  mov     rax, rsp
0x18003b0bf  mov     [rax+8], rbx
0x18003b0c3  mov     [rax+10h], rsi
0x18003b0c7  push    rdi
0x18003b0c8  sub     rsp, 30h
0x18003b0cc  mov     rdi, rcx
0x18003b0cf  mov     qword ptr [rax+20h], 0
0x18003b0d7  lea     rcx, [rax+18h]; pperrinfo
0x18003b0db  mov     qword ptr [rax+18h], 0
0x18003b0e3  mov     rsi, rdx
0x18003b0e6  call    cs:__imp_CreateErrorInfo
0x18003b0ed  nop     dword ptr [rax+rax+00h]
0x18003b0f2  mov     ebx, eax
0x18003b0f4  test    eax, eax
0x18003b0f6  js      short loc_18003B163
0x18003b0f8  mov     rcx, [rsp+38h+arg_10]
0x18003b0fd  mov     rdx, rdi
0x18003b100  mov     rax, [rcx]
0x18003b103  mov     rax, [rax+28h]
0x18003b107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b10c  mov     ebx, eax
0x18003b10e  test    eax, eax
0x18003b110  js      short loc_18003B163
0x18003b112  mov     rcx, [rsp+38h+arg_10]
0x18003b117  mov     rdx, rsi
0x18003b11a  mov     rax, [rcx]
0x18003b11d  mov     rax, [rax+18h]
0x18003b121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b126  mov     ebx, eax
0x18003b128  test    eax, eax
0x18003b12a  js      short loc_18003B163
0x18003b12c  mov     rcx, [rsp+38h+arg_10]
0x18003b131  lea     r8, [rsp+38h+perrinfo]
0x18003b136  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x18003b13d  mov     rax, [rcx]
0x18003b140  mov     rax, [rax]
0x18003b143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b148  mov     ebx, eax
0x18003b14a  test    eax, eax
0x18003b14c  js      short loc_18003B163
0x18003b14e  mov     rdx, [rsp+38h+perrinfo]; perrinfo
0x18003b153  xor     ecx, ecx; dwReserved
0x18003b155  call    cs:__imp_SetErrorInfo
0x18003b15c  nop     dword ptr [rax+rax+00h]
0x18003b161  mov     ebx, eax
0x18003b163  mov     rcx, [rsp+38h+perrinfo]; struct IUnknown *
0x18003b168  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18003b16d  mov     rcx, [rsp+38h+arg_10]; struct IUnknown *
0x18003b172  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18003b177  test    ebx, ebx
0x18003b179  jz      short loc_18003B1B0
0x18003b17b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b182  lea     rax, WPP_GLOBAL_Control
0x18003b189  cmp     rcx, rax
0x18003b18c  jz      short loc_18003B1B0
0x18003b18e  test    byte ptr [rcx+1Ch], 1
0x18003b192  jz      short loc_18003B1B0
0x18003b194  mov     rcx, [rcx+10h]
0x18003b198  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x18003b19f  mov     edx, 0Ch
0x18003b1a4  mov     [rsp+38h+var_18], ebx
0x18003b1a8  mov     r9, rdi
0x18003b1ab  call    WPP_SF_Sd
0x18003b1b0  mov     rsi, [rsp+38h+arg_8]
0x18003b1b5  mov     eax, ebx
0x18003b1b7  mov     rbx, [rsp+38h+arg_0]
0x18003b1bc  add     rsp, 30h
0x18003b1c0  pop     rdi
0x18003b1c1  retn
```
