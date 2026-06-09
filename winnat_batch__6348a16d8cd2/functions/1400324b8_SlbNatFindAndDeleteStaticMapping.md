# SlbNatFindAndDeleteStaticMapping

- ea: `0x1400324b8`
- end: `0x1400325f9`
- name: `SlbNatFindAndDeleteStaticMapping`
- size: `321`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002f9a0`

## callees

- `0x14000caa0`
- `0x14000d7f8`
- `0x1400310f8`
- `0x1400315a0`
- `0x1400324b8`
- `0x140032b0c`
- `0x1400344f8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032593`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140032593`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400324da`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1400324da`

## string_xrefs

- `0x1400325b9`: `Delete static mapping`

## pseudocode

```c
__int64 __fastcall SlbNatFindAndDeleteStaticMapping(wchar_t *Str2)
{
  __int64 Instance; // rax
  int v3; // esi
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 StaticMappingInInstance; // rdi
  __int64 v8; // r8
  __int64 v9; // r9
  _DWORD *v10; // rbx
  __int64 v11; // rax
  _QWORD *v12; // rcx
  _QWORD *v13; // rax
  PVOID *v14; // rdx
  int v15; // edx
  int v16; // r8d
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  P = 0;
  ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
  Instance = SlbNatFindInstance(Str2);
  v3 = Instance;
  if ( Instance )
  {
    StaticMappingInInstance = SlbNatFindStaticMappingInInstance(Instance, *((unsigned int *)Str2 + 20), &P);
    if ( StaticMappingInInstance )
    {
      v10 = P;
      if ( !P )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v8, v9);
      v11 = *(_QWORD *)StaticMappingInInstance;
      if ( *(_QWORD *)(*(_QWORD *)StaticMappingInInstance + 8LL) == StaticMappingInInstance )
      {
        v12 = *(_QWORD **)(StaticMappingInInstance + 8);
        if ( *v12 == StaticMappingInInstance )
        {
          *v12 = v11;
          *(_QWORD *)(v11 + 8) = v12;
          --v10[8];
          SlbNatDeleteStaticMapping((unsigned __int16 *)StaticMappingInInstance, v3);
          if ( (v10[23] & 1) == 0 || v10[8] )
            goto LABEL_13;
          v13 = *(_QWORD **)v10;
          if ( *(_DWORD **)(*(_QWORD *)v10 + 8LL) == v10 )
          {
            v14 = (PVOID *)*((_QWORD *)v10 + 1);
            if ( *v14 == v10 )
            {
              *v14 = v13;
              v13[1] = v14;
              SlbNatDeleteExternalAddress(v10);
LABEL_13:
              v4 = 0;
              goto LABEL_14;
            }
          }
        }
      }
      __fastfail(3u);
    }
  }
  v4 = -1073741275;
LABEL_14:
  ExReleaseResourceAndLeaveCriticalRegion(&Resource);
  if ( v4 < 0 && dword_140026104 == 1 && (byte_140026BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v15,
      v16,
      3009,
      (__int64)L"Delete static mapping",
      0,
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400324b8  mov     [rsp+arg_8], rbx
0x1400324bd  mov     [rsp+arg_10], rsi
0x1400324c2  push    rdi
0x1400324c3  sub     rsp, 40h
0x1400324c7  mov     rbx, rcx
0x1400324ca  mov     [rsp+48h+P], 0
0x1400324d3  lea     rcx, Resource; Resource
0x1400324da  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1400324e1  nop     dword ptr [rax+rax+00h]
0x1400324e6  mov     rcx, rbx; Str2
0x1400324e9  call    SlbNatFindInstance
0x1400324ee  mov     rsi, rax
0x1400324f1  test    rax, rax
0x1400324f4  jnz     short loc_140032500
0x1400324f6  mov     ebx, 0C0000225h
0x1400324fb  jmp     loc_14003258C
0x140032500  mov     edx, [rbx+50h]
0x140032503  lea     r8, [rsp+48h+P]
0x140032508  mov     rcx, rsi
0x14003250b  call    SlbNatFindStaticMappingInInstance
0x140032510  mov     rdi, rax
0x140032513  test    rax, rax
0x140032516  jz      short loc_1400324F6
0x140032518  mov     rbx, [rsp+48h+P]
0x14003251d  test    rbx, rbx
0x140032520  jnz     short loc_140032527
0x140032522  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140032527  mov     rax, [rdi]
0x14003252a  cmp     [rax+8], rdi
0x14003252e  jnz     loc_1400325F2
0x140032534  mov     rcx, [rdi+8]
0x140032538  cmp     [rcx], rdi
0x14003253b  jnz     loc_1400325F2
0x140032541  mov     [rcx], rax
0x140032544  mov     rdx, rsi
0x140032547  mov     [rax+8], rcx
0x14003254b  mov     rcx, rdi; P
0x14003254e  dec     dword ptr [rbx+20h]
0x140032551  call    SlbNatDeleteStaticMapping
0x140032556  test    byte ptr [rbx+5Ch], 1
0x14003255a  jz      short loc_14003258A
0x14003255c  cmp     dword ptr [rbx+20h], 0
0x140032560  jnz     short loc_14003258A
0x140032562  mov     rax, [rbx]
0x140032565  cmp     [rax+8], rbx
0x140032569  jnz     loc_1400325F2
0x14003256f  mov     rdx, [rbx+8]
0x140032573  cmp     [rdx], rbx
0x140032576  jnz     short loc_1400325F2
0x140032578  mov     [rdx], rax
0x14003257b  mov     rcx, rbx; P
0x14003257e  mov     [rax+8], rdx
0x140032582  mov     rdx, rsi
0x140032585  call    SlbNatDeleteExternalAddress
0x14003258a  xor     ebx, ebx
0x14003258c  lea     rcx, Resource; Resource
0x140032593  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14003259a  nop     dword ptr [rax+rax+00h]
0x14003259f  test    ebx, ebx
0x1400325a1  jns     short loc_1400325DF
0x1400325a3  cmp     cs:dword_140026104, 1
0x1400325aa  jnz     short loc_1400325DF
0x1400325ac  test    cs:byte_140026BED, 10h
0x1400325b3  jz      short loc_1400325DF
0x1400325b5  mov     [rsp+48h+var_18], ebx
0x1400325b9  lea     rax, aDeleteStaticMa; "Delete static mapping"
0x1400325c0  mov     [rsp+48h+var_20], 0
0x1400325c8  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400325cf  mov     r9d, 0BC1h
0x1400325d5  mov     [rsp+48h+var_28], rax
0x1400325da  call    McTemplateK0qzqq_EtwWriteTransfer
0x1400325df  mov     rsi, [rsp+48h+arg_10]
0x1400325e4  mov     eax, ebx
0x1400325e6  mov     rbx, [rsp+48h+arg_8]
0x1400325eb  add     rsp, 40h
0x1400325ef  pop     rdi
0x1400325f0  retn
0x1400325f2  mov     ecx, 3
0x1400325f7  int     29h; Win8: RtlFailFast(ecx)
```
