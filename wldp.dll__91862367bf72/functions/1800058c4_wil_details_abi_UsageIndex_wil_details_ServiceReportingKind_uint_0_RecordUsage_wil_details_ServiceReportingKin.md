# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x1800058c4`
- end: `0x180005ac5`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `513`
- prototype: `__int64 __fastcall(wil::details_abi::RawUsageIndex *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800051b0`

## callees

- `0x1800029c0`
- `0x180002c10`
- `0x180002c50`
- `0x180005898`
- `0x1800058c4`
- `0x180005d20`
- `0x180006814`
- `0x180006d00`
- `0x180015c00`
- `0x1800267f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000599d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000599d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000598f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000598f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        int a2,
        int a3)
{
  char v4; // si
  char **v5; // r14
  char *v6; // rax
  char *v7; // rdi
  char v8; // r12
  char *v9; // r15
  const char *v10; // r9
  void *v11; // r12
  HANDLE ProcessHeap; // rax
  __int64 v13; // rax
  void *v14; // rdi
  void *v15; // r14
  HANDLE v16; // rax
  char v18[8]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v19; // [rsp+38h] [rbp-28h]
  __int128 v20; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int Buf1; // [rsp+98h] [rbp+38h] BYREF
  int v23; // [rsp+A0h] [rbp+40h] BYREF

  v23 = a3;
  Buf1 = a2;
  v4 = 1;
  if ( !wil::details_abi::RawUsageIndex::RecordUsageInternal(this, &Buf1, 4u, &v23, 4u, 1u) )
  {
    v5 = (char **)((char *)this + 24);
    if ( *((_QWORD *)this + 3) )
    {
      if ( *((_BYTE *)this + 58) )
        wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), 0x28u);
    }
    else
    {
      v19 = 0;
      v20 = 0;
      wil::last_error_context::last_error_context((wil::last_error_context *)v18);
      v6 = (char *)wil::details::ProcessHeapAlloc(0, 0x40u);
      v7 = v6;
      if ( v6 )
      {
        memcpy_s(v6, 0x40u, 0, 0);
        wistd::unique_ptr<void,wil::process_heap_deleter>::reset((char *)&v20 + 8, v7);
        *(_QWORD *)&v19 = v7;
        *((_QWORD *)&v19 + 1) = v7;
        v9 = v7 + 64;
        *(_QWORD *)&v20 = v7 + 64;
        v8 = 1;
      }
      else
      {
        v8 = 0;
        v9 = 0;
      }
      wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
      if ( v8 )
      {
        if ( (unsigned __int64)(v9 - v7) < 0xA )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x14C9,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Staging.h",
            v10);
        v11 = (void *)*((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = 0;
        if ( v11 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v11);
        }
        *v5 = v7;
        *((_QWORD *)this + 5) = v9;
        *((_BYTE *)this + 57) = 0;
        *(_WORD *)v7 = 0;
        *((_WORD *)v7 + 1) = *(_WORD *)this;
        *((_WORD *)v7 + 2) = *((_WORD *)this + 1);
        v7[8] = *((_BYTE *)this + 4);
        *((_WORD *)v7 + 3) = *((_WORD *)this + 3);
        v7[9] = *((_BYTE *)this + 8);
        *((_QWORD *)this + 4) = *v5 + 10;
        v13 = *((_QWORD *)&v20 + 1);
        v14 = 0;
        *((_QWORD *)&v20 + 1) = 0;
        v15 = (void *)*((_QWORD *)this + 6);
        *((_QWORD *)this + 6) = v13;
        if ( v15 )
        {
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v15);
        }
        *((_BYTE *)this + 58) = 1;
      }
      else
      {
        v14 = (void *)*((_QWORD *)&v20 + 1);
      }
      *((_QWORD *)&v20 + 1) = 0;
      if ( v14 )
        MemoryFree(v14);
    }
    return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, &Buf1, 4u, &v23, 4u, 1u);
  }
  return v4;
}

```

## disassembly

```asm
0x1800058c4  mov     rax, rsp
0x1800058c7  mov     [rax+8], rbx
0x1800058cb  mov     [rax+20h], rsi
0x1800058cf  mov     [rax+18h], r8d
0x1800058d3  mov     [rax+10h], edx
0x1800058d6  push    rbp
0x1800058d7  push    rdi
0x1800058d8  push    r12
0x1800058da  push    r14
0x1800058dc  push    r15
0x1800058de  mov     rbp, rsp
0x1800058e1  sub     rsp, 60h
0x1800058e5  mov     rbx, rcx
0x1800058e8  mov     esi, 1
0x1800058ed  mov     [rax-60h], esi
0x1800058f0  lea     eax, [rsi+3]
0x1800058f3  mov     [rsp+60h+var_40], rax; size_t
0x1800058f8  lea     r9, [rbp+arg_10]; void *
0x1800058fc  mov     r8d, eax; Size
0x1800058ff  lea     rdx, [rbp+Buf1]; Buf1
0x180005903  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005908  test    al, al
0x18000590a  jnz     loc_180005A47
0x180005910  lea     r14, [rbx+18h]
0x180005914  cmp     qword ptr [r14], 0
0x180005918  jnz     loc_180005A69
0x18000591e  xorps   xmm0, xmm0
0x180005921  movdqu  [rbp+var_28], xmm0
0x180005926  xorps   xmm1, xmm1
0x180005929  movdqu  [rbp+var_18], xmm1
0x18000592e  lea     rcx, [rbp+var_30]; this
0x180005932  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180005937  nop
0x180005938  lea     r15d, [rsi+3Fh]
0x18000593c  mov     edx, r15d; dwBytes
0x18000593f  xor     ecx, ecx; dwFlags
0x180005941  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005946  mov     rdi, rax
0x180005949  test    rax, rax
0x18000594c  jnz     loc_180005A7E
0x180005952  xor     r12b, r12b
0x180005955  xor     r15d, r15d
0x180005958  lea     rcx, [rbp+var_30]; this
0x18000595c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180005961  test    r12b, r12b
0x180005964  jz      loc_180005A63
0x18000596a  mov     rcx, [rbp+28h]; this
0x18000596e  mov     rax, r15
0x180005971  sub     rax, rdi
0x180005974  cmp     rax, 0Ah
0x180005978  jb      loc_180005AB3
0x18000597e  mov     r12, [rbx+30h]
0x180005982  mov     qword ptr [rbx+30h], 0
0x18000598a  test    r12, r12
0x18000598d  jz      short loc_1800059A3
0x18000598f  call    cs:__imp_GetProcessHeap
0x180005995  mov     rcx, rax; hHeap
0x180005998  mov     r8, r12; lpMem
0x18000599b  xor     edx, edx; dwFlags
0x18000599d  call    cs:__imp_HeapFree
0x1800059a3  mov     [r14], rdi
0x1800059a6  mov     [rbx+28h], r15
0x1800059aa  mov     byte ptr [rbx+39h], 0
0x1800059ae  xor     eax, eax
0x1800059b0  mov     [rdi], ax
0x1800059b3  movzx   eax, word ptr [rbx]
0x1800059b6  mov     [rdi+2], ax
0x1800059ba  movzx   eax, word ptr [rbx+2]
0x1800059be  mov     [rdi+4], ax
0x1800059c2  mov     al, [rbx+4]
0x1800059c5  mov     [rdi+8], al
0x1800059c8  movzx   eax, word ptr [rbx+6]
0x1800059cc  mov     [rdi+6], ax
0x1800059d0  mov     al, [rbx+8]
0x1800059d3  mov     [rdi+9], al
0x1800059d6  mov     rax, [r14]
0x1800059d9  add     rax, 0Ah
0x1800059dd  mov     [rbx+20h], rax
0x1800059e1  mov     rax, qword ptr [rbp+var_18+8]
0x1800059e5  xor     edi, edi
0x1800059e7  mov     qword ptr [rbp+var_18+8], rdi
0x1800059eb  mov     r14, [rbx+30h]
0x1800059ef  mov     [rbx+30h], rax
0x1800059f3  test    r14, r14
0x1800059f6  jz      short loc_180005A0C
0x1800059f8  call    cs:__imp_GetProcessHeap
0x1800059fe  mov     rcx, rax; hHeap
0x180005a01  mov     r8, r14; lpMem
0x180005a04  xor     edx, edx; dwFlags
0x180005a06  call    cs:__imp_HeapFree
0x180005a0c  mov     [rbx+3Ah], sil
0x180005a10  mov     qword ptr [rbp+var_18+8], 0
0x180005a18  test    rdi, rdi
0x180005a1b  jz      short loc_180005A25
0x180005a1d  mov     rcx, rdi; void *
0x180005a20  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180005a25  mov     [rsp+60h+var_38], esi; unsigned int
0x180005a29  mov     r8d, 4; Size
0x180005a2f  mov     [rsp+60h+var_40], r8; size_t
0x180005a34  lea     r9, [rbp+arg_10]; void *
0x180005a38  lea     rdx, [rbp+Buf1]; Buf1
0x180005a3c  mov     rcx, rbx; this
0x180005a3f  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005a44  mov     sil, al
0x180005a47  mov     al, sil
0x180005a4a  lea     r11, [rsp+60h+var_s0]
0x180005a4f  mov     rbx, [r11+30h]
0x180005a53  mov     rsi, [r11+48h]
0x180005a57  mov     rsp, r11
0x180005a5a  pop     r15
0x180005a5c  pop     r14
0x180005a5e  pop     r12
0x180005a60  pop     rdi
0x180005a61  pop     rbp
0x180005a62  retn
0x180005a63  mov     rdi, qword ptr [rbp+var_18+8]
0x180005a67  jmp     short loc_180005A10
0x180005a69  cmp     byte ptr [rbx+3Ah], 0
0x180005a6d  jz      short loc_180005A25
0x180005a6f  mov     edx, 28h ; '('; unsigned __int64
0x180005a74  mov     rcx, r14; this
0x180005a77  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005a7c  jmp     short loc_180005A25
0x180005a7e  xor     r9d, r9d; SourceSize
0x180005a81  xor     r8d, r8d; Source
0x180005a84  mov     rdx, r15; DestinationSize
0x180005a87  mov     rcx, rdi; Destination
0x180005a8a  call    memcpy_s
0x180005a8f  mov     rdx, rdi
0x180005a92  lea     rcx, [rbp+var_18+8]
0x180005a96  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x180005a9b  mov     qword ptr [rbp+var_28], rdi
0x180005a9f  mov     qword ptr [rbp+var_28+8], rdi
0x180005aa3  lea     r15, [rdi+40h]
0x180005aa7  mov     qword ptr [rbp+var_18], r15
0x180005aab  mov     r12b, sil
0x180005aae  jmp     loc_180005958
0x180005ab3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Stagi"...
0x180005aba  mov     edx, 14C9h; void *
0x180005abf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
