# SlbNatFindAndDeleteStaticMapping

- ea: `0x1400335e8`
- end: `0x140033729`
- name: `SlbNatFindAndDeleteStaticMapping`
- size: `321`
- prototype: `__int64 __fastcall(wchar_t *Str2)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140030ad0`

## callees

- `0x14000caa0`
- `0x14000d7c8`
- `0x140032228`
- `0x1400326d0`
- `0x1400335e8`
- `0x140033c3c`
- `0x140035808`

## import_xrefs

- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400336c3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400336c3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14003360a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x14003360a`

## string_xrefs

- `0x1400336e9`: `Delete static mapping`

## pseudocode

```c
__int64 __fastcall SlbNatFindAndDeleteStaticMapping(wchar_t *Str2)
{
  __int64 Instance; // rax
  __int64 v3; // rsi
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 StaticMappingInInstance; // rdi
  __int64 v8; // r8
  _DWORD *v9; // rbx
  __int64 v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  PVOID *v13; // rdx
  int v14; // edx
  int v15; // r8d
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
      v9 = P;
      if ( !P )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, v5, v8);
      v10 = *(_QWORD *)StaticMappingInInstance;
      if ( *(_QWORD *)(*(_QWORD *)StaticMappingInInstance + 8LL) == StaticMappingInInstance )
      {
        v11 = *(_QWORD **)(StaticMappingInInstance + 8);
        if ( *v11 == StaticMappingInInstance )
        {
          *v11 = v10;
          *(_QWORD *)(v10 + 8) = v11;
          --v9[8];
          SlbNatDeleteStaticMapping((unsigned __int16 *)StaticMappingInInstance, v3);
          if ( (v9[23] & 1) == 0 || v9[8] )
            goto LABEL_13;
          v12 = *(_QWORD **)v9;
          if ( *(_DWORD **)(*(_QWORD *)v9 + 8LL) == v9 )
          {
            v13 = (PVOID *)*((_QWORD *)v9 + 1);
            if ( *v13 == v9 )
            {
              *v13 = v12;
              v12[1] = v13;
              SlbNatDeleteExternalAddress((char *)v9, v3);
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
  if ( v4 < 0 && dword_140027104 == 1 && (byte_140027BED & 0x10) != 0 )
    McTemplateK0qzqq_EtwWriteTransfer(
      (unsigned int)&MICROSOFT_WINNAT_ETW_PROVIDER_Context,
      v14,
      v15,
      3009,
      (__int64)L"Delete static mapping",
      0,
      v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400335e8  mov     [rsp+arg_8], rbx
0x1400335ed  mov     [rsp+arg_10], rsi
0x1400335f2  push    rdi
0x1400335f3  sub     rsp, 40h
0x1400335f7  mov     rbx, rcx
0x1400335fa  mov     [rsp+48h+P], 0
0x140033603  lea     rcx, Resource; Resource
0x14003360a  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140033611  nop     dword ptr [rax+rax+00h]
0x140033616  mov     rcx, rbx; Str2
0x140033619  call    SlbNatFindInstance
0x14003361e  mov     rsi, rax
0x140033621  test    rax, rax
0x140033624  jnz     short loc_140033630
0x140033626  mov     ebx, 0C0000225h
0x14003362b  jmp     loc_1400336BC
0x140033630  mov     edx, [rbx+50h]
0x140033633  lea     r8, [rsp+48h+P]
0x140033638  mov     rcx, rsi
0x14003363b  call    SlbNatFindStaticMappingInInstance
0x140033640  mov     rdi, rax
0x140033643  test    rax, rax
0x140033646  jz      short loc_140033626
0x140033648  mov     rbx, [rsp+48h+P]
0x14003364d  test    rbx, rbx
0x140033650  jnz     short loc_140033657
0x140033652  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140033657  mov     rax, [rdi]
0x14003365a  cmp     [rax+8], rdi
0x14003365e  jnz     loc_140033722
0x140033664  mov     rcx, [rdi+8]
0x140033668  cmp     [rcx], rdi
0x14003366b  jnz     loc_140033722
0x140033671  mov     [rcx], rax
0x140033674  mov     rdx, rsi
0x140033677  mov     [rax+8], rcx
0x14003367b  mov     rcx, rdi; P
0x14003367e  dec     dword ptr [rbx+20h]
0x140033681  call    SlbNatDeleteStaticMapping
0x140033686  test    byte ptr [rbx+5Ch], 1
0x14003368a  jz      short loc_1400336BA
0x14003368c  cmp     dword ptr [rbx+20h], 0
0x140033690  jnz     short loc_1400336BA
0x140033692  mov     rax, [rbx]
0x140033695  cmp     [rax+8], rbx
0x140033699  jnz     loc_140033722
0x14003369f  mov     rdx, [rbx+8]
0x1400336a3  cmp     [rdx], rbx
0x1400336a6  jnz     short loc_140033722
0x1400336a8  mov     [rdx], rax
0x1400336ab  mov     rcx, rbx; P
0x1400336ae  mov     [rax+8], rdx
0x1400336b2  mov     rdx, rsi
0x1400336b5  call    SlbNatDeleteExternalAddress
0x1400336ba  xor     ebx, ebx
0x1400336bc  lea     rcx, Resource; Resource
0x1400336c3  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400336ca  nop     dword ptr [rax+rax+00h]
0x1400336cf  test    ebx, ebx
0x1400336d1  jns     short loc_14003370F
0x1400336d3  cmp     cs:dword_140027104, 1
0x1400336da  jnz     short loc_14003370F
0x1400336dc  test    cs:byte_140027BED, 10h
0x1400336e3  jz      short loc_14003370F
0x1400336e5  mov     [rsp+48h+var_18], ebx
0x1400336e9  lea     rax, aDeleteStaticMa; "Delete static mapping"
0x1400336f0  mov     [rsp+48h+var_20], 0
0x1400336f8  lea     rcx, MICROSOFT_WINNAT_ETW_PROVIDER_Context
0x1400336ff  mov     r9d, 0BC1h
0x140033705  mov     [rsp+48h+var_28], rax
0x14003370a  call    McTemplateK0qzqq_EtwWriteTransfer
0x14003370f  mov     rsi, [rsp+48h+arg_10]
0x140033714  mov     eax, ebx
0x140033716  mov     rbx, [rsp+48h+arg_8]
0x14003371b  add     rsp, 40h
0x14003371f  pop     rdi
0x140033720  retn
0x140033722  mov     ecx, 3
0x140033727  int     29h; Win8: RtlFailFast(ecx)
```
