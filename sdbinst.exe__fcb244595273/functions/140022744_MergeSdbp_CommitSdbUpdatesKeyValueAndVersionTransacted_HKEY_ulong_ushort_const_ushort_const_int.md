# MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(HKEY__ *,ulong,ushort const *,ushort const *,int)

- ea: `0x140022744`
- end: `0x140022855`
- name: `?MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted@@YAKPEAUHKEY__@@KPEBG1H@Z`
- size: `273`
- prototype: `__int64 __fastcall(HKEY, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x14001008c`
- `0x140021934`
- `0x140022744`
- `0x14002285c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140022826`
- `KERNEL32!GetProcessHeap` at `0x140022826`
- `KERNEL32!HeapFree` at `0x140022834`
- `KERNEL32!HeapFree` at `0x140022834`

## string_xrefs

- `0x1400227e6`: `MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted`

## pseudocode

```c
__int64 __fastcall MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted(
        HKEY a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // edi
  void *v12; // rbx
  const unsigned __int16 *v13; // r9
  HANDLE ProcessHeap; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-10h] BYREF
  LPVOID lpMem; // [rsp+A0h] [rbp+40h] BYREF

  lpMem = 0;
  if ( a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
  }
  else
  {
    v9 = 0;
  }
  v16[0] = a3;
  v16[1] = v9;
  v17[0] = L"MergeVer_";
  v17[1] = 9;
  v18[0] = 0;
  v18[1] = 0;
  v10 = wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(
          &lpMem,
          v18,
          v17,
          v16);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v13 = a3;
    v12 = lpMem;
    v11 = MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted(a1, (const unsigned __int16 *)lpMem, a2, v13, a4, a5);
  }
  else
  {
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v10;
    AslLogCallPrintf(
      1,
      "MergeSdbp_CommitSdbUpdatesKeyValueAndVersionTransacted",
      1646,
      "Failed to concat merge version value (%d)",
      v11);
    v12 = lpMem;
  }
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v12);
  }
  return v11;
}

```

## disassembly

```asm
0x140022744  mov     [rsp-28h+arg_0], rbx
0x140022749  mov     [rsp-28h+arg_8], rsi
0x14002274e  push    rbp
0x14002274f  push    rdi
0x140022750  push    r12
0x140022752  push    r14
0x140022754  push    r15
0x140022756  mov     rbp, rsp
0x140022759  sub     rsp, 60h
0x14002275d  mov     rsi, r9
0x140022760  mov     rbx, r8
0x140022763  mov     r14d, edx
0x140022766  mov     r15, rcx
0x140022769  xor     r12d, r12d
0x14002276c  mov     [rbp+lpMem], r12
0x140022770  test    r8, r8
0x140022773  jz      short loc_140022785
0x140022775  or      rax, 0FFFFFFFFFFFFFFFFh
0x140022779  inc     rax
0x14002277c  cmp     [r8+rax*2], r12w
0x140022781  jnz     short loc_140022779
0x140022783  jmp     short loc_140022788
0x140022785  mov     rax, r12
0x140022788  mov     [rbp+var_30], rbx
0x14002278c  mov     [rbp+var_28], rax
0x140022790  lea     rax, aMergever_0; "MergeVer_"
0x140022797  mov     [rbp+var_20], rax
0x14002279b  mov     [rbp+var_18], 9
0x1400227a3  mov     [rbp+var_10], r12
0x1400227a7  mov     [rbp+var_8], r12
0x1400227ab  lea     r9, [rbp+var_30]
0x1400227af  lea     r8, [rbp+var_20]
0x1400227b3  lea     rdx, [rbp+var_10]
0x1400227b7  lea     rcx, [rbp+lpMem]
0x1400227bb  call    ??$str_build_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@Ustring_view_t@details@2@U342@U342@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@Ustring_view_t@01@11@Z; wil::details::str_build_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t,wil::details::string_view_t,wil::details::string_view_t)
0x1400227c0  mov     edi, eax
0x1400227c2  test    eax, eax
0x1400227c4  jns     short loc_1400227FE
0x1400227c6  and     eax, 1FFF0000h
0x1400227cb  cmp     eax, 70000h
0x1400227d0  jnz     short loc_1400227D5
0x1400227d2  movzx   edi, di
0x1400227d5  mov     dword ptr [rsp+60h+var_40], edi
0x1400227d9  lea     r9, aFailedToConcat_5; "Failed to concat merge version value (%"...
0x1400227e0  mov     r8d, 66Eh
0x1400227e6  lea     rdx, aMergesdbpCommi; "MergeSdbp_CommitSdbUpdatesKeyValueAndVe"...
0x1400227ed  mov     ecx, 1
0x1400227f2  call    AslLogCallPrintf
0x1400227f7  nop
0x1400227f8  mov     rbx, [rbp+lpMem]
0x1400227fc  jmp     short loc_140022821
0x1400227fe  mov     eax, [rbp+arg_20]
0x140022801  mov     [rsp+60h+var_38], eax; int
0x140022805  mov     [rsp+60h+var_40], rsi; unsigned __int16 *
0x14002280a  mov     r9, rbx; unsigned __int16 *
0x14002280d  mov     r8d, r14d; unsigned int
0x140022810  mov     rbx, [rbp+lpMem]
0x140022814  mov     rdx, rbx; unsigned __int16 *
0x140022817  mov     rcx, r15; HKEY
0x14002281a  call    ?MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted@@YAKPEAUHKEY__@@PEBGK11H@Z; MergeSdbp_CommitSdbUpdatesKeyValuePairTransacted(HKEY__ *,ushort const *,ulong,ushort const *,ushort const *,int)
0x14002281f  mov     edi, eax
0x140022821  test    rbx, rbx
0x140022824  jz      short loc_14002283A
0x140022826  call    cs:__imp_GetProcessHeap
0x14002282c  mov     r8, rbx; lpMem
0x14002282f  xor     edx, edx; dwFlags
0x140022831  mov     rcx, rax; hHeap
0x140022834  call    cs:__imp_HeapFree
0x14002283a  mov     eax, edi
0x14002283c  lea     r11, [rsp+60h+var_s0]
0x140022841  mov     rbx, [r11+30h]
0x140022845  mov     rsi, [r11+38h]
0x140022849  mov     rsp, r11
0x14002284c  pop     r15
0x14002284e  pop     r14
0x140022850  pop     r12
0x140022852  pop     rdi
0x140022853  pop     rbp
0x140022854  retn
```
