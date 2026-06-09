# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000a99c`
- end: `0x14000aabc`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `288`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140009d20`
- `0x14000a23c`
- `0x140013854`
- `0x140014184`
- `0x140014468`
- `0x140014764`
- `0x14001a310`

## callees

- `0x14000a788`
- `0x14000a99c`
- `0x1400206e0`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  char v9; // [rsp+30h] [rbp-38h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1, a2);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v9 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a99c  mov     rax, rsp
0x14000a99f  push    rbx
0x14000a9a0  push    rsi
0x14000a9a1  push    rdi
0x14000a9a2  sub     rsp, 50h
0x14000a9a6  mov     rsi, [rsp+68h+arg_20]
0x14000a9ae  mov     edi, edx
0x14000a9b0  mov     edx, [rax+38h]
0x14000a9b3  mov     r10, rcx
0x14000a9b6  test    edx, edx
0x14000a9b8  jz      loc_14000AAB4
0x14000a9be  mov     ebx, [rsp+68h+arg_28]
0x14000a9c5  mov     ecx, edx
0x14000a9c7  sub     ecx, 1
0x14000a9ca  jz      short loc_14000AA49
0x14000a9cc  sub     ecx, 1
0x14000a9cf  jz      short loc_14000AA3B
0x14000a9d1  sub     ecx, 1
0x14000a9d4  jz      short loc_14000AA2D
0x14000a9d6  sub     ecx, 1
0x14000a9d9  jz      short loc_14000AA1F
0x14000a9db  sub     ecx, 1
0x14000a9de  jz      short loc_14000AA11
0x14000a9e0  cmp     ecx, 1
0x14000a9e3  jz      short loc_14000AA03
0x14000a9e5  sub     dl, 64h ; 'd'
0x14000a9e8  cmp     dl, 31h ; '1'
0x14000a9eb  ja      short loc_14000AA56
0x14000a9ed  mov     eax, ebx
0x14000a9ef  neg     eax
0x14000a9f1  movzx   eax, dl
0x14000a9f4  sbb     ecx, ecx
0x14000a9f6  and     ecx, 0FFFFFFCEh
0x14000a9f9  add     ecx, 96h
0x14000a9ff  add     ecx, eax
0x14000aa01  jmp     short loc_14000AA5B
0x14000aa03  mov     eax, ebx
0x14000aa05  neg     eax
0x14000aa07  sbb     ecx, ecx
0x14000aa09  and     ecx, 0FFFFFFFEh
0x14000aa0c  add     ecx, 0Bh
0x14000aa0f  jmp     short loc_14000AA5B
0x14000aa11  mov     eax, ebx
0x14000aa13  neg     eax
0x14000aa15  sbb     ecx, ecx
0x14000aa17  and     ecx, 0FFFFFFFEh
0x14000aa1a  add     ecx, 0Ah
0x14000aa1d  jmp     short loc_14000AA5B
0x14000aa1f  mov     eax, ebx
0x14000aa21  neg     eax
0x14000aa23  sbb     ecx, ecx
0x14000aa25  and     ecx, 0FFFFFFFCh
0x14000aa28  add     ecx, 7
0x14000aa2b  jmp     short loc_14000AA5B
0x14000aa2d  mov     eax, ebx
0x14000aa2f  neg     eax
0x14000aa31  sbb     ecx, ecx
0x14000aa33  and     ecx, 0FFFFFFFCh
0x14000aa36  add     ecx, 6
0x14000aa39  jmp     short loc_14000AA5B
0x14000aa3b  mov     eax, ebx
0x14000aa3d  neg     eax
0x14000aa3f  sbb     ecx, ecx
0x14000aa41  and     ecx, 0FFFFFFFCh
0x14000aa44  add     ecx, 5
0x14000aa47  jmp     short loc_14000AA5B
0x14000aa49  mov     eax, ebx
0x14000aa4b  neg     eax
0x14000aa4d  sbb     ecx, ecx
0x14000aa4f  not     ecx
0x14000aa51  and     ecx, 4
0x14000aa54  jmp     short loc_14000AA5B
0x14000aa56  mov     ecx, 0FFh
0x14000aa5b  mov     al, [rsi+4]
0x14000aa5e  mov     edx, edi
0x14000aa60  mov     byte ptr [rsp+68h+var_30], al
0x14000aa64  mov     dword ptr [rsp+68h+var_48], ecx
0x14000aa68  mov     rcx, r10
0x14000aa6b  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000aa70  test    eax, eax
0x14000aa72  jz      short loc_14000AAB4
0x14000aa74  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000aa7b  test    rax, rax
0x14000aa7e  jz      short loc_14000AAB4
0x14000aa80  mov     [rsp+68h+var_30], 1
0x14000aa89  lea     rcx, [rsp+68h+arg_30]
0x14000aa91  mov     [rsp+68h+var_38], 0
0x14000aa96  mov     r9d, ebx
0x14000aa99  mov     [rsp+68h+var_40], 0
0x14000aaa2  xor     r8d, r8d
0x14000aaa5  mov     [rsp+68h+var_48], rcx
0x14000aaaa  mov     rdx, rsi
0x14000aaad  mov     ecx, edi
0x14000aaaf  call    _guard_dispatch_icall
0x14000aab4  add     rsp, 50h
0x14000aab8  pop     rdi
0x14000aab9  pop     rsi
0x14000aaba  pop     rbx
0x14000aabb  retn
```
