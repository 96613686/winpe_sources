# _GetWindowLongPtr(tagWND *,int,int)

- ea: `0x18000be40`
- end: `0x18000c162`
- name: `?_GetWindowLongPtr@@YA_KPEAUtagWND@@HH@Z`
- size: `802`
- prototype: `unsigned __int64(struct tagWND *, int, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000ad40`
- `0x18000bd00`
- `0x18000f140`
- `0x1800931cc`

## callees

- `0x18000ac60`
- `0x18000acb0`
- `0x18000b7d8`
- `0x18000be40`
- `0x1800107b0`
- `0x180050b44`

## import_xrefs

- `win32u!NtUserGetThreadState` at `0x18000c04b`
- `win32u!NtUserGetThreadState` at `0x18000c04b`
- `win32u!NtUserMessageCall` at `0x18000c08e`
- `win32u!NtUserMessageCall` at `0x18000c0d6`
- `win32u!NtUserMessageCall` at `0x18000c132`
- `win32u!NtUserMessageCall` at `0x18000c08e`
- `win32u!NtUserMessageCall` at `0x18000c0d6`
- `win32u!NtUserMessageCall` at `0x18000c132`
- `ntdll!RtlSetLastWin32Error` at `0x18000bf71`
- `ntdll!RtlSetLastWin32Error` at `0x18000bf83`
- `ntdll!RtlSetLastWin32Error` at `0x18000c005`
- `ntdll!RtlSetLastWin32Error` at `0x18000bf71`
- `ntdll!RtlSetLastWin32Error` at `0x18000bf83`
- `ntdll!RtlSetLastWin32Error` at `0x18000c005`

## pseudocode

```c
__int64 __fastcall _GetWindowLongPtr(struct tagWND *a1, int a2, int a3)
{
  __int64 v5; // rdx
  __int64 result; // rax
  unsigned int v8; // ecx
  int v9; // ebx
  unsigned __int64 v10; // rcx
  __int64 v11; // rdx
  PVOID v12; // rbp
  PVOID Win32ThreadInfo; // rax
  ULONG v14; // ecx
  __int64 v15; // rbx
  int v16; // edx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // edx
  __int64 *v22; // rax
  __int64 v23; // rbx
  __int64 CPD; // rax
  __int64 v25; // rbx
  int v26; // [rsp+50h] [rbp+8h] BYREF

  v5 = *((unsigned __int16 *)a1 + 21);
  if ( (*((_WORD *)a1 + 21) & 0x2FFF) == 0 )
  {
    if ( a2 < 0 )
      return GetWindowData(a1, a2, a3);
LABEL_5:
    v8 = *((_DWORD *)a1 + 62);
    if ( a2 >= v8 && (unsigned __int64)(a2 - v8) + 8 <= *((unsigned int *)a1 + 50) )
    {
LABEL_7:
      v9 = a2 - *((_DWORD *)a1 + 62);
      v10 = (unsigned __int16)*(_DWORD *)a1;
      if ( v10 < *(_QWORD *)(gSharedInfo + 8)
        && (v11 = qword_1800C9378 + (unsigned int)(dword_1800C9380 * v10), *(_BYTE *)(v11 + 24))
        && v11 )
      {
        v12 = *(PVOID *)(v11 + 8);
      }
      else
      {
        v12 = 0;
      }
      if ( NtCurrentTeb()->Win32ThreadInfo || (Win32ThreadInfo = (PVOID)NtUserGetThreadState(14)) != 0 )
        Win32ThreadInfo = NtCurrentTeb()->Win32ThreadInfo;
      if ( v12 == Win32ThreadInfo )
        return *(_QWORD *)(v9 + *((_QWORD *)a1 + 37));
      v18 = *(_QWORD *)a1;
      v26 = 0;
      result = NtUserMessageCall(v18, 90, v9, 2, &v26, 689, a3);
      if ( v26 )
        return *(_QWORD *)(v9 + *((_QWORD *)a1 + 37));
      return result;
    }
    goto LABEL_22;
  }
  if ( (*((_BYTE *)a1 + 18) & 1) == 0 )
  {
    if ( a2 < 0 )
      return GetWindowData(a1, a2, a3);
    if ( a2 >= *(unsigned __int16 *)(gpsi + 2LL * ((*((_WORD *)a1 + 21) & 0x2FFFu) - 666) + 328) )
      goto LABEL_5;
    v16 = v5 & 0x2FFF;
    if ( v16 == 679 )
    {
LABEL_29:
      if ( a2 )
      {
        RtlSetLastWin32Error(0x585u);
        return 0;
      }
      goto LABEL_7;
    }
    v21 = v16 - 677;
    if ( v21 )
    {
      if ( v21 == 5 )
        goto LABEL_29;
    }
    else
    {
      if ( !a2 )
      {
        v25 = *((_QWORD *)a1 + 37);
        if ( (unsigned int)TestWindowProcess(a1) )
          return **(_QWORD **)v25;
        return v25;
      }
      if ( a2 == 1 )
        return 2LL - ((*(_DWORD *)(**((_QWORD **)a1 + 37) + 116LL) & 0x400000) != 0);
    }
LABEL_22:
    v14 = 1413;
LABEL_23:
    RtlSetLastWin32Error(v14);
    return 0;
  }
  if ( a2 )
  {
    if ( a2 == 16 )
    {
      v17 = GETPTI(a1, v5);
      if ( v17 == PtiCurrent() )
        return *(_QWORD *)(*((_QWORD *)a1 + 37) + 16LL);
      v19 = *(_QWORD *)a1;
      v26 = 0;
      result = NtUserMessageCall(v19, 90, 16, 2, &v26, 689, a3);
      if ( v26 )
        return *(_QWORD *)(*((_QWORD *)a1 + 37) + 16LL);
    }
    else
    {
      if ( a2 != 8 )
      {
        if ( a2 < 0 )
          return GetWindowData(a1, a2, a3);
        if ( a2 < 30 )
        {
          RtlSetLastWin32Error(0x587u);
          return 0;
        }
        goto LABEL_5;
      }
      if ( !(unsigned int)TestWindowProcess(a1) )
      {
        v14 = 5;
        goto LABEL_23;
      }
      v22 = *(__int64 **)(*((_QWORD *)a1 + 37) + 8LL);
      v23 = *v22;
      if ( *v22 )
      {
        if ( a3 != ((*((_DWORD *)v22 + 6) >> 2) & 1) )
        {
          CPD = GetCPD(a1, 66 - (unsigned int)(a3 != 0), v23);
          if ( CPD )
            return CPD;
        }
      }
      return v23;
    }
  }
  else
  {
    v15 = GETPTI(a1, v5);
    if ( v15 == PtiCurrent() )
      return **((_QWORD **)a1 + 37);
    v20 = *(_QWORD *)a1;
    v26 = 0;
    result = NtUserMessageCall(v20, 90, 0, 2, &v26, 689, a3);
    if ( v26 )
      return **((_QWORD **)a1 + 37);
  }
  return result;
}

```

## disassembly

```asm
0x18000be40  mov     [rsp+arg_10], rbx
0x18000be45  mov     [rsp+arg_18], rsi
0x18000be4a  push    rdi
0x18000be4b  sub     rsp, 40h
0x18000be4f  mov     ebx, edx
0x18000be51  mov     esi, r8d
0x18000be54  movzx   edx, word ptr [rcx+2Ah]
0x18000be58  mov     rdi, rcx
0x18000be5b  mov     eax, edx
0x18000be5d  and     eax, 0FFFF2FFFh
0x18000be62  jnz     loc_18000BF3F
0x18000be68  test    ebx, ebx
0x18000be6a  jns     short loc_18000BE83
0x18000be6c  mov     edx, ebx; int
0x18000be6e  call    ?GetWindowData@@YA_KPEAUtagWND@@HH@Z; GetWindowData(tagWND *,int,int)
0x18000be73  mov     rbx, [rsp+48h+arg_10]
0x18000be78  mov     rsi, [rsp+48h+arg_18]
0x18000be7d  add     rsp, 40h
0x18000be81  pop     rdi
0x18000be82  retn
0x18000be83  mov     ecx, [rdi+0F8h]
0x18000be89  cmp     ebx, ecx
0x18000be8b  jb      loc_18000BF7E
0x18000be91  mov     eax, ebx
0x18000be93  sub     eax, ecx
0x18000be95  mov     ecx, eax
0x18000be97  mov     eax, [rdi+0C8h]
0x18000be9d  add     rcx, 8
0x18000bea1  cmp     rcx, rax
0x18000bea4  ja      loc_18000BF7E
0x18000beaa  mov     eax, [rdi]
0x18000beac  sub     ebx, [rdi+0F8h]
0x18000beb2  movzx   ecx, ax
0x18000beb5  mov     rax, cs:gSharedInfo
0x18000bebc  mov     [rsp+48h+arg_8], rbp
0x18000bec1  cmp     rcx, [rax+8]
0x18000bec5  jnb     loc_18000C012
0x18000becb  imul    ecx, cs:dword_1800C9380
0x18000bed2  mov     edx, ecx
0x18000bed4  add     rdx, cs:qword_1800C9378
0x18000bedb  cmp     byte ptr [rdx+18h], 0
0x18000bedf  jz      loc_18000C012
0x18000bee5  test    rdx, rdx
0x18000bee8  jz      loc_18000C012
0x18000beee  mov     rbp, [rdx+8]
0x18000bef2  mov     rax, gs:30h
0x18000befb  cmp     qword ptr [rax+78h], 0
0x18000bf00  jz      loc_18000C046
0x18000bf06  mov     rax, gs:30h
0x18000bf0f  mov     rax, [rax+78h]
0x18000bf13  cmp     rbp, rax
0x18000bf16  mov     rbp, [rsp+48h+arg_8]
0x18000bf1b  jnz     loc_18000C05F
0x18000bf21  mov     rax, [rdi+128h]
0x18000bf28  movsxd  rcx, ebx
0x18000bf2b  mov     rax, [rcx+rax]
0x18000bf2f  mov     rbx, [rsp+48h+arg_10]
0x18000bf34  mov     rsi, [rsp+48h+arg_18]
0x18000bf39  add     rsp, 40h
0x18000bf3d  pop     rdi
0x18000bf3e  retn
0x18000bf3f  test    byte ptr [rcx+12h], 1
0x18000bf43  jz      short loc_18000BFC0
0x18000bf45  test    ebx, ebx
0x18000bf47  jz      short loc_18000BF90
0x18000bf49  cmp     ebx, 10h
0x18000bf4c  jz      loc_18000C019
0x18000bf52  cmp     ebx, 8
0x18000bf55  jz      loc_18000C0EC
0x18000bf5b  test    ebx, ebx
0x18000bf5d  js      loc_18000BE6C
0x18000bf63  cmp     ebx, 1Eh
0x18000bf66  jge     loc_18000BE83
0x18000bf6c  mov     ecx, 587h; LastError
0x18000bf71  call    cs:__imp_RtlSetLastWin32Error
0x18000bf77  xor     eax, eax
0x18000bf79  jmp     loc_18000BE73
0x18000bf7e  mov     ecx, 585h; LastError
0x18000bf83  call    cs:__imp_RtlSetLastWin32Error
0x18000bf89  xor     eax, eax
0x18000bf8b  jmp     loc_18000BE73
0x18000bf90  call    _GETPTI
0x18000bf95  mov     rbx, rax
0x18000bf98  call    PtiCurrent
0x18000bf9d  cmp     rbx, rax
0x18000bfa0  jnz     loc_18000C103
0x18000bfa6  mov     rax, [rdi+128h]
0x18000bfad  mov     rax, [rax]
0x18000bfb0  mov     rbx, [rsp+48h+arg_10]
0x18000bfb5  mov     rsi, [rsp+48h+arg_18]
0x18000bfba  add     rsp, 40h
0x18000bfbe  pop     rdi
0x18000bfbf  retn
0x18000bfc0  test    ebx, ebx
0x18000bfc2  js      loc_18000BE6C
0x18000bfc8  add     eax, 0FFFFFD66h
0x18000bfcd  mov     ecx, eax
0x18000bfcf  mov     rax, cs:gpsi
0x18000bfd6  movzx   ecx, word ptr [rax+rcx*2+148h]
0x18000bfde  cmp     ebx, ecx
0x18000bfe0  jge     loc_18000BE83
0x18000bfe6  and     edx, 0FFFF2FFFh
0x18000bfec  cmp     edx, 2A7h
0x18000bff2  jnz     loc_18000C148
0x18000bff8  test    ebx, ebx
0x18000bffa  jz      loc_18000BEAA
0x18000c000  mov     ecx, 585h; LastError
0x18000c005  call    cs:__imp_RtlSetLastWin32Error
0x18000c00b  xor     eax, eax
0x18000c00d  jmp     loc_18000BE73
0x18000c012  xor     ebp, ebp
0x18000c014  jmp     loc_18000BEF2
0x18000c019  call    _GETPTI
0x18000c01e  mov     rbx, rax
0x18000c021  call    PtiCurrent
0x18000c026  cmp     rbx, rax
0x18000c029  jnz     short loc_18000C0A4
0x18000c02b  mov     rax, [rdi+128h]
0x18000c032  mov     rbx, [rsp+48h+arg_10]
0x18000c037  mov     rsi, [rsp+48h+arg_18]
0x18000c03c  mov     rax, [rax+10h]
0x18000c040  add     rsp, 40h
0x18000c044  pop     rdi
0x18000c045  retn
0x18000c046  mov     ecx, 0Eh
0x18000c04b  call    cs:__imp_NtUserGetThreadState
0x18000c051  test    rax, rax
0x18000c054  jnz     loc_18000BF06
0x18000c05a  jmp     loc_18000BF13
0x18000c05f  mov     rcx, [rdi]
0x18000c062  lea     rax, [rsp+48h+arg_0]
0x18000c067  mov     [rsp+48h+var_18], esi
0x18000c06b  mov     edx, 5Ah ; 'Z'
0x18000c070  mov     [rsp+48h+var_20], 2B1h
0x18000c078  mov     r9d, 2
0x18000c07e  movsxd  r8, ebx
0x18000c081  mov     [rsp+48h+var_28], rax
0x18000c086  mov     [rsp+48h+arg_0], 0
0x18000c08e  call    cs:__imp_NtUserMessageCall
0x18000c094  cmp     [rsp+48h+arg_0], 0
0x18000c099  jz      loc_18000BE73
0x18000c09f  jmp     loc_18000BF21
0x18000c0a4  mov     rcx, [rdi]
0x18000c0a7  lea     rax, [rsp+48h+arg_0]
0x18000c0ac  mov     [rsp+48h+var_18], esi
0x18000c0b0  mov     edx, 5Ah ; 'Z'
0x18000c0b5  mov     [rsp+48h+var_20], 2B1h
0x18000c0bd  mov     r9d, 2
0x18000c0c3  mov     r8d, 10h
0x18000c0c9  mov     [rsp+48h+var_28], rax
0x18000c0ce  mov     [rsp+48h+arg_0], 0
0x18000c0d6  call    cs:__imp_NtUserMessageCall
0x18000c0dc  cmp     [rsp+48h+arg_0], 0
0x18000c0e1  jz      loc_18000BE73
0x18000c0e7  jmp     loc_18000C02B
0x18000c0ec  call    TestWindowProcess
0x18000c0f1  test    eax, eax
0x18000c0f3  jnz     loc_18009876E
0x18000c0f9  mov     ecx, 5
0x18000c0fe  jmp     loc_18000BF83
0x18000c103  mov     rcx, [rdi]
0x18000c106  lea     rax, [rsp+48h+arg_0]
0x18000c10b  mov     [rsp+48h+var_18], esi
0x18000c10f  mov     r9d, 2
0x18000c115  mov     [rsp+48h+var_20], 2B1h
0x18000c11d  xor     r8d, r8d
0x18000c120  mov     edx, 5Ah ; 'Z'
0x18000c125  mov     [rsp+48h+var_28], rax
0x18000c12a  mov     [rsp+48h+arg_0], 0
0x18000c132  call    cs:__imp_NtUserMessageCall
0x18000c138  cmp     [rsp+48h+arg_0], 0
0x18000c13d  jz      loc_18000BE73
0x18000c143  jmp     loc_18000BFA6
0x18000c148  sub     edx, 2A5h
0x18000c14e  jz      loc_1800987AF
0x18000c154  cmp     edx, 5
0x18000c157  jz      loc_18000BFF8
0x18000c15d  jmp     loc_18000BF7E
0x18009876e  mov     rax, [rdi+128h]
0x180098775  mov     rax, [rax+8]
0x180098779  mov     rbx, [rax]
0x18009877c  test    rbx, rbx
0x18009877f  jz      short loc_1800987A7
0x180098781  mov     eax, [rax+18h]
0x180098784  shr     eax, 2
0x180098787  and     eax, 1
0x18009878a  cmp     esi, eax
0x18009878c  jz      short loc_1800987A7
0x18009878e  neg     esi
0x180098790  mov     r8, rbx
0x180098793  mov     rcx, rdi
0x180098796  sbb     edx, edx
0x180098798  add     edx, 42h ; 'B'
0x18009879b  call    GetCPD
0x1800987a0  test    rax, rax
0x1800987a3  cmovnz  rbx, rax
0x1800987a7  mov     rax, rbx
0x1800987aa  jmp     loc_18000BE73
0x1800987af  test    ebx, ebx
0x1800987b1  jnz     short loc_1800987D4
0x1800987b3  mov     rbx, [rdi+128h]
0x1800987ba  mov     rcx, rdi
0x1800987bd  call    TestWindowProcess
0x1800987c2  test    eax, eax
0x1800987c4  jz      short loc_1800987CC
0x1800987c6  mov     rax, [rbx]
0x1800987c9  mov     rbx, [rax]
0x1800987cc  mov     rax, rbx
0x1800987cf  jmp     loc_18000BE73
0x1800987d4  cmp     ebx, 1
0x1800987d7  jnz     loc_18000BF7E
0x1800987dd  mov     rax, [rdi+128h]
0x1800987e4  mov     rcx, [rax]
0x1800987e7  mov     eax, [rcx+74h]
0x1800987ea  and     eax, 400000h
0x1800987ef  neg     eax
0x1800987f1  sbb     rax, rax
0x1800987f4  add     rax, 2
0x1800987f8  jmp     loc_18000BE73
```
