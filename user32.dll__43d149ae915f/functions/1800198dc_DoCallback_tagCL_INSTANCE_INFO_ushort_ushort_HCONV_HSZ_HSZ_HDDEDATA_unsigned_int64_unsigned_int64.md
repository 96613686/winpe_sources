# DoCallback(tagCL_INSTANCE_INFO *,ushort,ushort,HCONV__ *,HSZ__ *,HSZ__ *,HDDEDATA__ *,unsigned __int64,unsigned __int64)

- ea: `0x1800198dc`
- end: `0x180019b1a`
- name: `?DoCallback@@YAPEAUHDDEDATA__@@PEAUtagCL_INSTANCE_INFO@@GGPEAUHCONV__@@PEAUHSZ__@@2PEAU1@_K4@Z`
- size: `574`
- prototype: `HDDEDATA __fastcall(struct tagCL_INSTANCE_INFO *, unsigned __int16, unsigned __int16, HCONV, HSZ, HSZ, HDDEDATA hData, unsigned __int64, unsigned __int64)`
- caller_count: `12`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180019c04`
- `0x180045fc0`
- `0x180048434`
- `0x18005e2b4`
- `0x180062d00`
- `0x18008f9b0`
- `0x1800900d0`
- `0x1800902b4`
- `0x1800903f4`
- `0x180090590`
- `0x180090768`
- `0x18009095c`

## callees

- `0x1800198dc`
- `0x1800481f4`
- `0x180048720`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserEvent` at `0x180019ad6`
- `win32u!NtUserEvent` at `0x180019ad6`
- `ntdll!RtlEnterCriticalSection` at `0x180019995`
- `ntdll!RtlEnterCriticalSection` at `0x180019b00`
- `ntdll!RtlEnterCriticalSection` at `0x180019995`
- `ntdll!RtlEnterCriticalSection` at `0x180019b00`
- `ntdll!RtlLeaveCriticalSection` at `0x180019934`
- `ntdll!RtlLeaveCriticalSection` at `0x180019a98`
- `ntdll!RtlLeaveCriticalSection` at `0x180019934`
- `ntdll!RtlLeaveCriticalSection` at `0x180019a98`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800199c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800199c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019af3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019af3`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180019ae0`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180019aea`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180019ae0`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180019aea`

## pseudocode

```c
__int64 __fastcall DoCallback(
        struct tagCL_INSTANCE_INFO *a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned __int64 a4,
        HSZ a5,
        HSZ a6,
        HDDEDATA hData,
        unsigned __int64 a8,
        unsigned __int64 a9)
{
  unsigned int v9; // edi
  unsigned int v11; // r15d
  struct _TEB *v14; // rbx
  __int64 v15; // r14
  char *v16; // rax
  char *v17; // rbx
  HDDEDATA v18; // rcx

  v9 = a3;
  v11 = a2;
  if ( a4 && ((a4 >> 7) & 7) == 7 )
    return 0;
  v14 = NtCurrentTeb();
  ++HIDWORD(v14->Win32ClientInfo[11]);
  ++*((_WORD *)a1 + 55);
  RtlLeaveCriticalSection(&gcsDDEML);
  v15 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, HSZ, HSZ, HDDEDATA, unsigned __int64, unsigned __int64))a1
         + 8))(
          v11,
          v9,
          a4,
          a5,
          a6,
          hData,
          a8,
          a9);
  RtlEnterCriticalSection(&gcsDDEML);
  --*((_WORD *)a1 + 55);
  --HIDWORD(v14->Win32ClientInfo[11]);
  if ( (*((_BYTE *)a1 + 56) & 1) == 0 && (*((_DWORD *)a1 + 6) & 0x8000000) != 0 )
  {
    v16 = (char *)LocalAlloc(0x40u, 0xA0u);
    v17 = v16;
    if ( v16 )
    {
      *(_DWORD *)v16 = 0x8000000;
      *((_WORD *)v16 + 2) = 1;
      *((_WORD *)v16 + 3) = 152;
      *((_DWORD *)v16 + 2) = 152;
      *((_DWORD *)v16 + 3) = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
      *((_QWORD *)v16 + 2) = *((int *)a1 + 19);
      *((_DWORD *)v16 + 6) = v15;
      *((_DWORD *)v16 + 7) = v11;
      *((_DWORD *)v16 + 8) = v9;
      *((_QWORD *)v16 + 5) = a4;
      *((_QWORD *)v16 + 6) = LocalToGlobalAtom((unsigned __int16)a5);
      *((_QWORD *)v17 + 7) = LocalToGlobalAtom((unsigned __int16)a6);
      *((_QWORD *)v17 + 10) = a9;
      *((_QWORD *)v17 + 8) = hData;
      *((_QWORD *)v17 + 9) = a8;
      if ( (_WORD)v11 == 4194 || (_WORD)v11 == 8418 )
      {
        if ( a8 )
        {
          *(_OWORD *)(v17 + 88) = *(_OWORD *)a8;
          *(_OWORD *)(v17 + 104) = *(_OWORD *)(a8 + 16);
          *((_DWORD *)v17 + 30) = *(_DWORD *)(a8 + 32);
        }
      }
      RtlLeaveCriticalSection(&gcsDDEML);
      if ( (v11 & 0x2000) != 0 )
      {
        if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v18 = (HDDEDATA)v15;
LABEL_16:
          *((_DWORD *)v17 + 31) = DdeGetData(v18, (LPBYTE)v17 + 128, 0x20u, 0);
        }
      }
      else if ( hData )
      {
        v18 = hData;
        goto LABEL_16;
      }
      NtUserEvent(v17);
      GlobalDeleteAtom(*((_WORD *)v17 + 24));
      GlobalDeleteAtom(*((_WORD *)v17 + 28));
      LocalFree(v17);
      RtlEnterCriticalSection(&gcsDDEML);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800198dc  push    rbx
0x1800198de  push    rbp
0x1800198df  push    rsi
0x1800198e0  push    rdi
0x1800198e1  push    r12
0x1800198e3  push    r13
0x1800198e5  push    r14
0x1800198e7  push    r15
0x1800198e9  sub     rsp, 58h
0x1800198ed  movzx   edi, r8w
0x1800198f1  mov     rbp, r9
0x1800198f4  movzx   r15d, dx
0x1800198f8  mov     rsi, rcx
0x1800198fb  test    r9, r9
0x1800198fe  jz      short loc_180019915
0x180019900  mov     rax, r9
0x180019903  shr     rax, 7
0x180019907  and     eax, 7
0x18001990a  cmp     al, 7
0x18001990c  jnz     short loc_180019915
0x18001990e  xor     eax, eax
0x180019910  jmp     loc_180019B09
0x180019915  mov     rbx, gs:30h
0x18001991e  mov     eax, 1
0x180019923  add     [rbx+85Ch], eax
0x180019929  add     [rcx+6Eh], ax
0x18001992d  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019934  call    cs:__imp_RtlLeaveCriticalSection
0x18001993a  mov     rcx, [rsp+98h+arg_40]
0x180019942  mov     r13d, edi
0x180019945  mov     rdi, [rsp+98h+arg_38]
0x18001994d  mov     r8, rbp
0x180019950  mov     r12, [rsp+98h+hData]
0x180019958  mov     edx, r13d
0x18001995b  mov     r9, [rsp+98h+arg_20]
0x180019963  mov     rax, [rsi+40h]
0x180019967  mov     [rsp+98h+var_60], rcx
0x18001996c  mov     rcx, [rsp+98h+arg_28]
0x180019974  mov     [rsp+98h+var_68], rdi
0x180019979  mov     [rsp+98h+var_70], r12
0x18001997e  mov     [rsp+98h+var_78], rcx
0x180019983  mov     ecx, r15d
0x180019986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001998b  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019992  mov     r14, rax
0x180019995  call    cs:__imp_RtlEnterCriticalSection
0x18001999b  or      eax, 0FFFFFFFFh
0x18001999e  add     [rsi+6Eh], ax
0x1800199a2  add     [rbx+85Ch], eax
0x1800199a8  test    byte ptr [rsi+38h], 1
0x1800199ac  jnz     loc_180019B06
0x1800199b2  test    dword ptr [rsi+18h], 8000000h
0x1800199b9  jz      loc_180019B06
0x1800199bf  mov     edx, 0A0h; uBytes
0x1800199c4  lea     ecx, [rax+41h]; uFlags
0x1800199c7  call    cs:__imp_LocalAlloc
0x1800199cd  mov     rbx, rax
0x1800199d0  test    rax, rax
0x1800199d3  jz      loc_180019B06
0x1800199d9  movzx   ecx, word ptr [rsp+98h+arg_20]; unsigned __int16
0x1800199e1  mov     edx, 7FFE0320h
0x1800199e6  mov     dword ptr [rax], 8000000h
0x1800199ec  mov     word ptr [rax+4], 1
0x1800199f2  mov     eax, 98h
0x1800199f7  mov     [rbx+6], ax
0x1800199fb  mov     [rbx+8], eax
0x1800199fe  mov     rdx, [rdx]
0x180019a01  mov     r8d, ds:7FFE0004h
0x180019a09  imul    r8, rdx
0x180019a0d  shr     r8, 18h
0x180019a11  mov     [rbx+0Ch], r8d
0x180019a15  movsxd  rax, dword ptr [rsi+4Ch]
0x180019a19  mov     [rbx+10h], rax
0x180019a1d  mov     [rbx+18h], r14d
0x180019a21  mov     [rbx+1Ch], r15d
0x180019a25  mov     [rbx+20h], r13d
0x180019a29  mov     [rbx+28h], rbp
0x180019a2d  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180019a32  movzx   ecx, word ptr [rsp+98h+arg_28]; unsigned __int16
0x180019a3a  movzx   eax, ax
0x180019a3d  mov     [rbx+30h], rax
0x180019a41  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180019a46  movzx   eax, ax
0x180019a49  mov     [rbx+38h], rax
0x180019a4d  mov     rax, [rsp+98h+arg_40]
0x180019a55  mov     [rbx+50h], rax
0x180019a59  mov     eax, 1062h
0x180019a5e  mov     [rbx+40h], r12
0x180019a62  mov     [rbx+48h], rdi
0x180019a66  cmp     r15w, ax
0x180019a6a  jz      short loc_180019A77
0x180019a6c  mov     eax, 20E2h
0x180019a71  cmp     r15w, ax
0x180019a75  jnz     short loc_180019A91
0x180019a77  test    rdi, rdi
0x180019a7a  jz      short loc_180019A91
0x180019a7c  movups  xmm0, xmmword ptr [rdi]
0x180019a7f  movups  xmmword ptr [rbx+58h], xmm0
0x180019a83  movups  xmm1, xmmword ptr [rdi+10h]
0x180019a87  movups  xmmword ptr [rbx+68h], xmm1
0x180019a8b  mov     eax, [rdi+20h]
0x180019a8e  mov     [rbx+78h], eax
0x180019a91  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019a98  call    cs:__imp_RtlLeaveCriticalSection
0x180019a9e  bt      r15w, 0Dh
0x180019aa4  jnb     short loc_180019AB5
0x180019aa6  lea     rax, [r14-1]
0x180019aaa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019aae  ja      short loc_180019AD3
0x180019ab0  mov     rcx, r14
0x180019ab3  jmp     short loc_180019ABD
0x180019ab5  test    r12, r12
0x180019ab8  jz      short loc_180019AD3
0x180019aba  mov     rcx, r12; hData
0x180019abd  xor     r9d, r9d; cbOff
0x180019ac0  lea     rdx, [rbx+80h]; pDst
0x180019ac7  lea     r8d, [r9+20h]; cbMax
0x180019acb  call    DdeGetData
0x180019ad0  mov     [rbx+7Ch], eax
0x180019ad3  mov     rcx, rbx
0x180019ad6  call    cs:__imp_NtUserEvent
0x180019adc  movzx   ecx, word ptr [rbx+30h]; nAtom
0x180019ae0  call    cs:__imp_GlobalDeleteAtom
0x180019ae6  movzx   ecx, word ptr [rbx+38h]; nAtom
0x180019aea  call    cs:__imp_GlobalDeleteAtom
0x180019af0  mov     rcx, rbx; hMem
0x180019af3  call    cs:__imp_LocalFree
0x180019af9  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180019b00  call    cs:__imp_RtlEnterCriticalSection
0x180019b06  mov     rax, r14
0x180019b09  add     rsp, 58h
0x180019b0d  pop     r15
0x180019b0f  pop     r14
0x180019b11  pop     r13
0x180019b13  pop     r12
0x180019b15  pop     rdi
0x180019b16  pop     rsi
0x180019b17  pop     rbp
0x180019b18  pop     rbx
0x180019b19  retn
```
