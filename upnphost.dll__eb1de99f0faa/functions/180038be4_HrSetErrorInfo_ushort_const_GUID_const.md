# HrSetErrorInfo(ushort const *,_GUID const &)

- ea: `0x180038be4`
- end: `0x180038cde`
- name: `?HrSetErrorInfo@@YAJPEBGAEBU_GUID@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035320`
- `0x180035770`
- `0x18004c230`
- `0x18004cb90`

## callees

- `0x18001ef30`
- `0x180038be4`
- `0x180046540`
- `0x180055010`

## import_xrefs

- `combase!CreateErrorInfo` at `0x180038c0e`
- `combase!CreateErrorInfo` at `0x180038c0e`
- `combase!SetErrorInfo` at `0x180038c77`
- `combase!SetErrorInfo` at `0x180038c77`

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
0x180038be4  mov     rax, rsp
0x180038be7  mov     [rax+8], rbx
0x180038beb  mov     [rax+10h], rsi
0x180038bef  push    rdi
0x180038bf0  sub     rsp, 30h
0x180038bf4  mov     rdi, rcx
0x180038bf7  mov     qword ptr [rax+20h], 0
0x180038bff  lea     rcx, [rax+18h]; pperrinfo
0x180038c03  mov     qword ptr [rax+18h], 0
0x180038c0b  mov     rsi, rdx
0x180038c0e  call    cs:__imp_CreateErrorInfo
0x180038c14  mov     ebx, eax
0x180038c16  test    eax, eax
0x180038c18  js      short loc_180038C7F
0x180038c1a  mov     rcx, [rsp+38h+arg_10]
0x180038c1f  mov     rdx, rdi
0x180038c22  mov     rax, [rcx]
0x180038c25  mov     rax, [rax+28h]
0x180038c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c2e  mov     ebx, eax
0x180038c30  test    eax, eax
0x180038c32  js      short loc_180038C7F
0x180038c34  mov     rcx, [rsp+38h+arg_10]
0x180038c39  mov     rdx, rsi
0x180038c3c  mov     rax, [rcx]
0x180038c3f  mov     rax, [rax+18h]
0x180038c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c48  mov     ebx, eax
0x180038c4a  test    eax, eax
0x180038c4c  js      short loc_180038C7F
0x180038c4e  mov     rcx, [rsp+38h+arg_10]
0x180038c53  lea     r8, [rsp+38h+perrinfo]
0x180038c58  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x180038c5f  mov     rax, [rcx]
0x180038c62  mov     rax, [rax]
0x180038c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c6a  mov     ebx, eax
0x180038c6c  test    eax, eax
0x180038c6e  js      short loc_180038C7F
0x180038c70  mov     rdx, [rsp+38h+perrinfo]; perrinfo
0x180038c75  xor     ecx, ecx; dwReserved
0x180038c77  call    cs:__imp_SetErrorInfo
0x180038c7d  mov     ebx, eax
0x180038c7f  mov     rcx, [rsp+38h+perrinfo]; struct IUnknown *
0x180038c84  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180038c89  mov     rcx, [rsp+38h+arg_10]; struct IUnknown *
0x180038c8e  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180038c93  test    ebx, ebx
0x180038c95  jz      short loc_180038CCC
0x180038c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c9e  lea     rax, WPP_GLOBAL_Control
0x180038ca5  cmp     rcx, rax
0x180038ca8  jz      short loc_180038CCC
0x180038caa  test    byte ptr [rcx+1Ch], 1
0x180038cae  jz      short loc_180038CCC
0x180038cb0  mov     rcx, [rcx+10h]
0x180038cb4  lea     r8, WPP_0f8e6464007c3e0bdd6d585d5cfe4b6e_Traceguids
0x180038cbb  mov     edx, 0Ch
0x180038cc0  mov     [rsp+38h+var_18], ebx
0x180038cc4  mov     r9, rdi
0x180038cc7  call    WPP_SF_Sd
0x180038ccc  mov     rsi, [rsp+38h+arg_8]
0x180038cd1  mov     eax, ebx
0x180038cd3  mov     rbx, [rsp+38h+arg_0]
0x180038cd8  add     rsp, 30h
0x180038cdc  pop     rdi
0x180038cdd  retn
```
