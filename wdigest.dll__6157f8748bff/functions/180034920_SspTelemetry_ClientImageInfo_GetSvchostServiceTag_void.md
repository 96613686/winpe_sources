# SspTelemetry::ClientImageInfo::GetSvchostServiceTag(void)

- ea: `0x180034920`
- end: `0x180034b1a`
- name: `?GetSvchostServiceTag@ClientImageInfo@SspTelemetry@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `506`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180034b20`
- `0x180034cd0`

## callees

- `0x180034920`
- `0x180034ebc`
- `0x180034f00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003495e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003495e`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034a15`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034ae1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034a15`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034ae1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800349ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800349f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034aef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800349ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800349f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034a7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034ac1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034aef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034afc`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180034993`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180034a49`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180034993`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180034a49`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall SspTelemetry::ClientImageInfo::GetSvchostServiceTag(__int64 a1, _QWORD *a2)
{
  unsigned __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rdi
  void *v7; // rax
  void *v8; // rsi
  unsigned __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rsi
  void *v14; // rax
  void *v15; // r14
  _DWORD v17[2]; // [rsp+20h] [rbp-40h] BYREF
  HLOCAL v18; // [rsp+28h] [rbp-38h]
  HLOCAL *v19; // [rsp+30h] [rbp-30h]
  char v20; // [rsp+38h] [rbp-28h]
  __int128 v21; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h]
  HLOCAL v23; // [rsp+A0h] [rbp+40h] BYREF

  *a2 = 0;
  if ( !(unsigned int)_o__wcsnicmp(a1 + 32, L"svchost", 7) )
  {
    v21 = 0;
    hMem = 0;
    LODWORD(v21) = *(_DWORD *)(a1 + 8);
    DWORD1(v21) = NtCurrentTeb()->SubProcessTag;
    if ( (unsigned int)I_QueryTagInformation(0, 1, &v21) )
    {
      v17[1] = 0;
      v18 = 0;
      v17[0] = *(_DWORD *)(a1 + 8);
      if ( !(unsigned int)I_QueryTagInformation(0, 3, v17) )
      {
        v23 = v18;
        if ( v18 )
        {
          v19 = &v23;
          v20 = 1;
          if ( *(_DWORD *)v18 == 1
            && (v10 = *((_QWORD *)v18 + 1), *(_DWORD *)v10 == 1)
            && (v11 = *(_QWORD *)(v10 + 8)) != 0 )
          {
            v12 = -1;
            do
              ++v12;
            while ( *(_WORD *)(v11 + 2 * v12) );
            v13 = v12 + 1;
            v14 = SspTelemetry::TelemetryAllocate((SspTelemetry *)(2 * (v12 + 1)), v9);
            v15 = v14;
            if ( v14 )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                a2,
                v14);
              _o_wcsncpy_s(v15, v13, v11, v13);
            }
            LocalFree(v23);
          }
          else
          {
            LocalFree(v18);
          }
        }
      }
    }
    else
    {
      v19 = (HLOCAL *)&v21;
      v20 = 1;
      if ( hMem )
      {
        v5 = -1;
        do
          ++v5;
        while ( *((_WORD *)hMem + v5) );
        v6 = v5 + 1;
        v7 = SspTelemetry::TelemetryAllocate((SspTelemetry *)(2 * (v5 + 1)), v4);
        v8 = v7;
        if ( v7 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            a2,
            v7);
          _o_wcsncpy_s(v8, v6, hMem, v6);
        }
        LocalFree(hMem);
      }
      else
      {
        LocalFree(0);
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180034920  mov     [rsp-28h+arg_18], rbx
0x180034925  mov     [rsp-28h+arg_8], rdx
0x18003492a  push    rbp
0x18003492b  push    rsi
0x18003492c  push    rdi
0x18003492d  push    r14
0x18003492f  push    r15
0x180034931  mov     rbp, rsp
0x180034934  sub     rsp, 60h
0x180034938  mov     rbx, rdx
0x18003493b  mov     rdi, rcx
0x18003493e  mov     esi, 1
0x180034943  mov     [rbp+arg_0], esi
0x180034946  xor     r15d, r15d
0x180034949  mov     [rdx], r15
0x18003494c  mov     [rbp+arg_0], esi
0x18003494f  add     rcx, 20h ; ' '
0x180034953  lea     r8d, [rsi+6]
0x180034957  lea     rdx, aSvchost; "svchost"
0x18003495e  call    cs:__imp__o__wcsnicmp
0x180034964  test    eax, eax
0x180034966  jnz     loc_180034B03
0x18003496c  xorps   xmm0, xmm0
0x18003496f  xor     eax, eax
0x180034971  movups  [rbp+var_20], xmm0
0x180034975  mov     [rbp+hMem], rax
0x180034979  mov     eax, [rdi+8]
0x18003497c  mov     dword ptr [rbp+var_20], eax
0x18003497f  mov     rax, gs:1720h
0x180034988  mov     dword ptr [rbp+var_20+4], eax
0x18003498b  lea     r8, [rbp+var_20]
0x18003498f  mov     edx, esi
0x180034991  xor     ecx, ecx
0x180034993  call    cs:__imp_I_QueryTagInformation
0x180034999  test    eax, eax
0x18003499b  jnz     loc_180034A2F
0x1800349a1  lea     rax, [rbp+var_20]
0x1800349a5  mov     [rbp+var_30], rax
0x1800349a9  mov     [rbp+var_28], sil
0x1800349ad  mov     rcx, [rbp+hMem]; hMem
0x1800349b1  test    rcx, rcx
0x1800349b4  jnz     short loc_1800349C6
0x1800349b6  mov     [rbp+arg_0], r15d
0x1800349ba  call    cs:__imp_LocalFree
0x1800349c0  nop
0x1800349c1  jmp     loc_180034B03
0x1800349c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800349ca  inc     rax
0x1800349cd  cmp     [rcx+rax*2], r15w
0x1800349d2  jnz     short loc_1800349CA
0x1800349d4  lea     rdi, [rax+1]
0x1800349d8  lea     rcx, [rdi+rdi]; this
0x1800349dc  call    ?TelemetryAllocate@SspTelemetry@@YAPEAX_K@Z; SspTelemetry::TelemetryAllocate(unsigned __int64)
0x1800349e1  mov     rsi, rax
0x1800349e4  test    rax, rax
0x1800349e7  jnz     short loc_1800349FD
0x1800349e9  mov     [rbp+arg_0], r15d
0x1800349ed  mov     rcx, [rbp+hMem]; hMem
0x1800349f1  call    cs:__imp_LocalFree
0x1800349f7  nop
0x1800349f8  jmp     loc_180034B03
0x1800349fd  mov     rdx, rsi
0x180034a00  mov     rcx, rbx
0x180034a03  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034a08  mov     r9, rdi
0x180034a0b  mov     r8, [rbp+hMem]
0x180034a0f  mov     rdx, rdi
0x180034a12  mov     rcx, rsi
0x180034a15  call    cs:__imp__o_wcsncpy_s
0x180034a1b  mov     [rbp+arg_0], r15d
0x180034a1f  mov     rcx, [rbp+hMem]; hMem
0x180034a23  call    cs:__imp_LocalFree
0x180034a29  nop
0x180034a2a  jmp     loc_180034B03
0x180034a2f  xor     eax, eax
0x180034a31  mov     [rbp+var_3C], eax
0x180034a34  mov     [rbp+var_38], rax
0x180034a38  mov     eax, [rdi+8]
0x180034a3b  mov     [rbp+var_40], eax
0x180034a3e  lea     r8, [rbp+var_40]
0x180034a42  mov     edx, 3
0x180034a47  xor     ecx, ecx
0x180034a49  call    cs:__imp_I_QueryTagInformation
0x180034a4f  test    eax, eax
0x180034a51  jnz     loc_180034B03
0x180034a57  mov     rcx, [rbp+var_38]; hMem
0x180034a5b  mov     [rbp+arg_10], rcx
0x180034a5f  test    rcx, rcx
0x180034a62  jz      loc_180034B03
0x180034a68  lea     rax, [rbp+arg_10]
0x180034a6c  mov     [rbp+var_30], rax
0x180034a70  mov     [rbp+var_28], sil
0x180034a74  cmp     [rcx], esi
0x180034a76  jz      short loc_180034A85
0x180034a78  mov     [rbp+arg_0], r15d
0x180034a7c  call    cs:__imp_LocalFree
0x180034a82  nop
0x180034a83  jmp     short loc_180034B03
0x180034a85  mov     rdi, [rcx+8]
0x180034a89  cmp     [rdi], esi
0x180034a8b  jnz     short loc_180034AF8
0x180034a8d  mov     rdi, [rdi+8]
0x180034a91  test    rdi, rdi
0x180034a94  jz      short loc_180034AF8
0x180034a96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180034a9a  inc     rax
0x180034a9d  cmp     [rdi+rax*2], r15w
0x180034aa2  jnz     short loc_180034A9A
0x180034aa4  lea     rsi, [rax+1]
0x180034aa8  lea     rcx, [rsi+rsi]; this
0x180034aac  call    ?TelemetryAllocate@SspTelemetry@@YAPEAX_K@Z; SspTelemetry::TelemetryAllocate(unsigned __int64)
0x180034ab1  mov     r14, rax
0x180034ab4  test    rax, rax
0x180034ab7  jnz     short loc_180034ACA
0x180034ab9  mov     [rbp+arg_0], r15d
0x180034abd  mov     rcx, [rbp+arg_10]; hMem
0x180034ac1  call    cs:__imp_LocalFree
0x180034ac7  nop
0x180034ac8  jmp     short loc_180034B03
0x180034aca  mov     rdx, r14
0x180034acd  mov     rcx, rbx
0x180034ad0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?TelemetryFree@SspTelemetry@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&SspTelemetry::TelemetryFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034ad5  mov     r9, rsi
0x180034ad8  mov     r8, rdi
0x180034adb  mov     rdx, rsi
0x180034ade  mov     rcx, r14
0x180034ae1  call    cs:__imp__o_wcsncpy_s
0x180034ae7  mov     [rbp+arg_0], r15d
0x180034aeb  mov     rcx, [rbp+arg_10]; hMem
0x180034aef  call    cs:__imp_LocalFree
0x180034af5  nop
0x180034af6  jmp     short loc_180034B03
0x180034af8  mov     [rbp+arg_0], r15d
0x180034afc  call    cs:__imp_LocalFree
0x180034b02  nop
0x180034b03  mov     rax, rbx
0x180034b06  mov     rbx, [rsp+60h+arg_18]
0x180034b0e  add     rsp, 60h
0x180034b12  pop     r15
0x180034b14  pop     r14
0x180034b16  pop     rdi
0x180034b17  pop     rsi
0x180034b18  pop     rbp
0x180034b19  retn
```
