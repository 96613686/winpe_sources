# CNodeFactory::XMLParser_Element_doc_assembly_noInheritable(ushort,_SXS_NODE_INFO const *)

- ea: `0x18002e290`
- end: `0x18002e498`
- name: `?XMLParser_Element_doc_assembly_noInheritable@CNodeFactory@@QEAAHGPEBU_SXS_NODE_INFO@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(CNodeFactory *__hidden this, unsigned __int16, const struct _SXS_NODE_INFO *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x18000df40`
- `0x18002e290`
- `0x18002e4a0`
- `0x1800515ec`
- `0x18005d428`
- `0x180067548`
- `0x180067680`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlPopFrame` at `0x18002e3ca`
- `ntdll!RtlPopFrame` at `0x18002e3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e47e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e47e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e417`

## pseudocode

```c
__int64 __fastcall CNodeFactory::XMLParser_Element_doc_assembly_noInheritable(
        CNodeFactory *this,
        __int16 a2,
        const struct _SXS_NODE_INFO *a3)
{
  int v5; // eax
  __int64 v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int v10; // edx
  unsigned int v11; // r8d
  DWORD LastError; // eax
  struct _UNICODE_STRING *v13; // [rsp+30h] [rbp-120h]
  struct _UNICODE_STRING *v14; // [rsp+38h] [rbp-118h]
  const struct _UNICODE_STRING *v15; // [rsp+40h] [rbp-110h]
  const struct _UNICODE_STRING *v16; // [rsp+48h] [rbp-108h]
  const struct _UNICODE_STRING *v17; // [rsp+50h] [rbp-100h]
  const struct _UNICODE_STRING *v18; // [rsp+58h] [rbp-F8h]
  const struct _UNICODE_STRING *v19; // [rsp+60h] [rbp-F0h]
  const struct _UNICODE_STRING *v20; // [rsp+68h] [rbp-E8h]
  const struct _UNICODE_STRING *v21; // [rsp+70h] [rbp-E0h]
  const struct _UNICODE_STRING *v22; // [rsp+78h] [rbp-D8h]
  const struct _UNICODE_STRING *v23; // [rsp+80h] [rbp-D0h]
  const struct _UNICODE_STRING *v24; // [rsp+88h] [rbp-C8h]
  const struct _UNICODE_STRING *v25; // [rsp+90h] [rbp-C0h]
  const struct _UNICODE_STRING *v26; // [rsp+98h] [rbp-B8h]
  const struct _UNICODE_STRING *v27; // [rsp+A0h] [rbp-B0h]
  const struct _UNICODE_STRING *v28; // [rsp+A8h] [rbp-A8h]
  const struct _UNICODE_STRING *v29; // [rsp+B0h] [rbp-A0h]
  struct _UNICODE_STRING v30; // [rsp+D0h] [rbp-80h] BYREF
  struct _UNICODE_STRING v31; // [rsp+E0h] [rbp-70h] BYREF
  int v32; // [rsp+F0h] [rbp-60h] BYREF
  struct _TEB_ACTIVE_FRAME Frame; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v34; // [rsp+110h] [rbp-40h]
  int v35; // [rsp+118h] [rbp-38h]
  int *v36; // [rsp+120h] [rbp-30h]

  v34 = 544438355;
  v32 = 0;
  Frame.Context = (PCTEB_ACTIVE_FRAME_CONTEXT)&qword_18006E108;
  Frame.Previous = 0;
  v35 = 2305;
  Frame.Flags = 1;
  v36 = &v32;
  CFrame::BaseEnter((CFrame *)&Frame);
  v5 = *((_DWORD *)this + 94);
  if ( v5 != 1 )
  {
    if ( (unsigned int)(v5 - 2) > 1 )
    {
      SetLastError(0x54Fu);
      *v36 = 0;
      goto LABEL_6;
    }
    v10 = -1056899024;
    v11 = 134;
    goto LABEL_14;
  }
  if ( a2 != 1 )
  {
    v10 = -1056899026;
    v11 = 131;
LABEL_14:
    CNodeFactory::LogParseError(
      this,
      v10,
      v11,
      0,
      0,
      0,
      v13,
      v14,
      v15,
      v16,
      v17,
      v18,
      v19,
      v20,
      v21,
      v22,
      v23,
      v24,
      v25,
      v26,
      v27,
      v28,
      v29);
    goto LABEL_6;
  }
  if ( *((_BYTE *)this + 1839) )
  {
    v10 = -1056899006;
    v11 = 141;
    goto LABEL_14;
  }
  if ( *((_BYTE *)this + 1833) )
  {
    v6 = *((_QWORD *)this + 2);
    v7 = *((unsigned int *)this + 118);
    v30.Buffer = (PWSTR)L"assemblyIdentity";
    *(_DWORD *)&v30.Length = 2097184;
    v31.Buffer = (PWSTR)L"noInheritable";
    *(_DWORD *)&v31.Length = 1703962;
    TraceActCtxGenManifestParseError(*(_DWORD *)(v6 + 1304), v7, L"noInheritable", L"assemblyIdentity", 0, 0x85u);
    FusionpLogParseError(
      *(const unsigned __int16 **)(*((_QWORD *)this + 2) + 1312LL),
      *((const unsigned __int16 **)this + 56),
      *((_QWORD *)this + 57),
      *((_DWORD *)this + 118),
      0xC1010049,
      &v31,
      &v30,
      0);
  }
  else
  {
    *((_BYTE *)this + 1839) = 1;
    v32 = 1;
  }
LABEL_6:
  v8 = v32;
  if ( g_FusionEnterExitTracingEnabled )
  {
    if ( *v36 )
    {
      FusionpTraceCallSuccessfulExit(0);
    }
    else
    {
      LastError = GetLastError();
      FusionpTraceCallWin32UnsuccessfulExit(LastError, 0);
    }
  }
  RtlPopFrame(&Frame);
  return v8;
}

```

## disassembly

```asm
0x18002e290  mov     [rsp-8+arg_8], rbx
0x18002e295  mov     [rsp-8+arg_10], rsi
0x18002e29a  push    rbp
0x18002e29b  push    rdi
0x18002e29c  push    r14
0x18002e29e  lea     rbp, [rsp+20h]
0x18002e2a3  sub     rsp, 130h
0x18002e2aa  mov     rax, cs:__security_cookie
0x18002e2b1  xor     rax, rsp
0x18002e2b4  mov     [rbp-10h+var_18], rax
0x18002e2b8  xor     esi, esi
0x18002e2ba  mov     [rbp-10h+var_30], 20737853h
0x18002e2c2  lea     rax, qword_18006E108
0x18002e2c9  mov     [rbp-10h+var_50], esi
0x18002e2cc  mov     [rbp-10h+Frame.Context], rax
0x18002e2d0  mov     rbx, rcx
0x18002e2d3  lea     rax, [rbp-10h+var_50]
0x18002e2d7  mov     [rbp-10h+Frame.Previous], rsi
0x18002e2db  lea     r14d, [rsi+1]
0x18002e2df  mov     [rbp-10h+var_28], 901h
0x18002e2e6  lea     rcx, [rbp-10h+Frame]; this
0x18002e2ea  mov     [rbp-10h+Frame.Flags], r14d
0x18002e2ee  movzx   edi, dx
0x18002e2f1  mov     [rbp-10h+var_20], rax
0x18002e2f5  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x18002e2fa  mov     eax, [rbx+178h]
0x18002e300  cmp     eax, r14d
0x18002e303  jnz     loc_18002E40A
0x18002e309  cmp     di, r14w
0x18002e30d  jnz     loc_18002E438
0x18002e313  cmp     [rbx+72Fh], sil
0x18002e31a  jnz     loc_18002E445
0x18002e320  cmp     [rbx+729h], sil
0x18002e327  jz      loc_18002E3FD
0x18002e32d  mov     rcx, [rbx+10h]
0x18002e331  lea     r9, aAssemblyidenti; "assemblyIdentity"
0x18002e338  mov     edx, [rbx+1D8h]; unsigned int
0x18002e33e  lea     r8, aNoinheritable; "noInheritable"
0x18002e345  mov     [rbp-10h+var_70.Buffer], r9
0x18002e349  mov     dword ptr [rbp-10h+var_70.Length], 200020h
0x18002e350  mov     [rbp-10h+var_60.Buffer], r8
0x18002e354  mov     dword ptr [rbp-10h+var_60.Length], 1A001Ah
0x18002e35b  mov     ecx, [rcx+518h]; int
0x18002e361  mov     word ptr [rsp+140h+var_118], 85h; unsigned __int16
0x18002e368  mov     qword ptr [rsp+140h+dwMessageId], rsi; unsigned __int16 *
0x18002e36d  call    ?TraceActCtxGenManifestParseError@@YAKJKPEBG00G@Z; TraceActCtxGenManifestParseError(long,ulong,ushort const *,ushort const *,ushort const *,ushort)
0x18002e372  mov     rcx, [rbx+10h]
0x18002e376  lea     rax, [rbp-10h+var_70]
0x18002e37a  mov     r9d, [rbx+1D8h]; unsigned int
0x18002e381  mov     r8, [rbx+1C8h]; unsigned __int64
0x18002e388  mov     rdx, [rbx+1C0h]; unsigned __int16 *
0x18002e38f  mov     rcx, [rcx+520h]; unsigned __int16 *
0x18002e396  mov     [rsp+140h+var_108], rsi; struct _UNICODE_STRING *
0x18002e39b  mov     [rsp+140h+var_110], rax; struct _UNICODE_STRING *
0x18002e3a0  lea     rax, [rbp-10h+var_60]
0x18002e3a4  mov     [rsp+140h+var_118], rax; struct _UNICODE_STRING *
0x18002e3a9  mov     [rsp+140h+dwMessageId], 0C1010049h; dwMessageId
0x18002e3b1  call    ?FusionpLogParseError@@YAJPEBG0_KKKPEBU_UNICODE_STRING@@2222222222222222222@Z; FusionpLogParseError(ushort const *,ushort const *,unsigned __int64,ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002e3b6  cmp     cs:g_FusionEnterExitTracingEnabled, sil
0x18002e3bd  mov     ebx, [rbp-10h+var_50]
0x18002e3c0  jnz     loc_18002E46A
0x18002e3c6  lea     rcx, [rbp-10h+Frame]; Frame
0x18002e3ca  call    cs:__imp_RtlPopFrame
0x18002e3d1  nop     dword ptr [rax+rax+00h]
0x18002e3d6  mov     eax, ebx
0x18002e3d8  mov     rcx, [rbp-10h+var_18]
0x18002e3dc  xor     rcx, rsp; StackCookie
0x18002e3df  call    __security_check_cookie
0x18002e3e4  lea     r11, [rsp+140h+var_10]
0x18002e3ec  mov     rbx, [r11+28h]
0x18002e3f0  mov     rsi, [r11+30h]
0x18002e3f4  mov     rsp, r11
0x18002e3f7  pop     r14
0x18002e3f9  pop     rdi
0x18002e3fa  pop     rbp
0x18002e3fb  retn
0x18002e3fd  mov     [rbx+72Fh], r14b
0x18002e404  mov     [rbp-10h+var_50], r14d
0x18002e408  jmp     short loc_18002E3B6
0x18002e40a  add     eax, 0FFFFFFFEh
0x18002e40d  cmp     eax, r14d
0x18002e410  jbe     short loc_18002E42B
0x18002e412  mov     ecx, 54Fh; dwErrCode
0x18002e417  call    cs:__imp_SetLastError
0x18002e41e  nop     dword ptr [rax+rax+00h]
0x18002e423  mov     rax, [rbp-10h+var_20]
0x18002e427  mov     [rax], esi
0x18002e429  jmp     short loc_18002E3B6
0x18002e42b  mov     edx, 0C1010030h
0x18002e430  mov     r8d, 86h
0x18002e436  jmp     short loc_18002E450
0x18002e438  mov     edx, 0C101002Eh
0x18002e43d  mov     r8d, 83h
0x18002e443  jmp     short loc_18002E450
0x18002e445  mov     edx, 0C1010042h; unsigned int
0x18002e44a  mov     r8d, 8Dh; unsigned int
0x18002e450  mov     [rsp+140h+var_118], rsi; struct _UNICODE_STRING *
0x18002e455  xor     r9d, r9d; struct _UNICODE_STRING *
0x18002e458  mov     rcx, rbx; this
0x18002e45b  mov     qword ptr [rsp+140h+dwMessageId], rsi; struct _UNICODE_STRING *
0x18002e460  call    ?LogParseError@CNodeFactory@@QEAAJKKPEBU_UNICODE_STRING@@0000000000000000000@Z; CNodeFactory::LogParseError(ulong,ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x18002e465  jmp     loc_18002E3B6
0x18002e46a  mov     rax, [rbp-10h+var_20]
0x18002e46e  cmp     [rax], esi
0x18002e470  jz      short loc_18002E47E
0x18002e472  xor     ecx, ecx; char *
0x18002e474  call    ?FusionpTraceCallSuccessfulExit@@YAXPEBDZZ; FusionpTraceCallSuccessfulExit(char const *,...)
0x18002e479  jmp     loc_18002E3C6
0x18002e47e  call    cs:__imp_GetLastError
0x18002e485  nop     dword ptr [rax+rax+00h]
0x18002e48a  mov     ecx, eax; unsigned int
0x18002e48c  xor     edx, edx; Format
0x18002e48e  call    ?FusionpTraceCallWin32UnsuccessfulExit@@YAXKPEBDZZ; FusionpTraceCallWin32UnsuccessfulExit(ulong,char const *,...)
0x18002e493  jmp     loc_18002E3C6
```
