# TRequestMakeCall

- ea: `0x18002fc10`
- end: `0x18002ff71`
- name: `TRequestMakeCall`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x1800072e4`
- `0x18001abb8`
- `0x18001c854`
- `0x18002a6e0`
- `0x18002c8d4`
- `0x18002fc10`
- `0x18003dc84`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18002fd20`
- `KERNEL32!HeapAlloc` at `0x18002fd20`
- `KERNEL32!LeaveCriticalSection` at `0x18002fc79`
- `KERNEL32!LeaveCriticalSection` at `0x18002fec3`
- `KERNEL32!LeaveCriticalSection` at `0x18002ff38`
- `KERNEL32!LeaveCriticalSection` at `0x18002fc79`
- `KERNEL32!LeaveCriticalSection` at `0x18002fec3`
- `KERNEL32!LeaveCriticalSection` at `0x18002ff38`
- `KERNEL32!EnterCriticalSection` at `0x18002fc42`
- `KERNEL32!EnterCriticalSection` at `0x18002fe12`
- `KERNEL32!EnterCriticalSection` at `0x18002fc42`
- `KERNEL32!EnterCriticalSection` at `0x18002fe12`

## string_xrefs

- `0x18002fdf9`: `   Comment: [%ls]`

## pseudocode

```c
void __fastcall TRequestMakeCall(__int64 a1, _DWORD *a2, unsigned int a3, _DWORD *a4, _DWORD *a5)
{
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  const wchar_t *v15; // r11
  const wchar_t *v16; // r11
  const wchar_t *v17; // r11
  __int64 v18; // rcx

  if ( a2[7] )
  {
    EnterCriticalSection(&gPriorityListCritSec);
    v8 = lpMem;
    if ( lpMem )
    {
      do
      {
        v9 = (_QWORD *)v8[60];
        ServerFree(v8);
        v8 = v9;
      }
      while ( v9 );
    }
    qword_180051950 = 0;
    lpMem = 0;
    LeaveCriticalSection(&gPriorityListCritSec);
    TRACELogPrint(0x10002u, "TRequestMakeCall: couldn't exec proxy, deleting requests");
    *a2 = -2;
  }
  else if ( IsBadStringParam(a3, (__int64)a4, a2[2])
         || (v10 = a2[3], v10 != -1) && IsBadStringParam(a3, (__int64)a4, v10)
         || (v11 = a2[4], v11 != -1) && IsBadStringParam(a3, (__int64)a4, v11)
         || (v12 = a2[5], v12 != -1) && IsBadStringParam(a3, (__int64)a4, v12)
         || a2[6] > a3
         || (v13 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, 0x1E8u), (v14 = v13) == 0) )
  {
    *a2 = -16;
  }
  else
  {
    TRACELogPrint(0x40002u, "Request:  0x%p", v13);
    StringCbCopyW(v14, 0xA0u, (STRSAFE_LPCWSTR)((char *)a4 + (unsigned int)a2[2]));
    TRACELogPrint(0x40002u, "   DestAddress: [%ls]", v14);
    if ( a2[3] != -1 )
    {
      StringCbCopyW(v14 + 80, 0x50u, (STRSAFE_LPCWSTR)((char *)a4 + (unsigned int)a2[3]));
      TRACELogPrint(0x40002u, "   AppName: [%ls]", v15);
    }
    if ( a2[4] != -1 )
    {
      StringCbCopyW(v14 + 120, 0x50u, (STRSAFE_LPCWSTR)((char *)a4 + (unsigned int)a2[4]));
      TRACELogPrint(0x40002u, "   CalledParty: [%ls]", v16);
    }
    if ( a2[5] != -1 )
    {
      StringCbCopyW(v14 + 160, 0xA0u, (STRSAFE_LPCWSTR)((char *)a4 + (unsigned int)a2[5]));
      TRACELogPrint(0x40002u, "   Comment: [%ls]", v17);
    }
    EnterCriticalSection(&gPriorityListCritSec);
    if ( qword_180051950 )
    {
      *(_QWORD *)(qword_180051950 + 480) = v14;
      v18 = 0;
    }
    else
    {
      lpMem = v14;
      v18 = 1;
    }
    qword_180051950 = (__int64)v14;
    *a4 = a2[6];
    a4[2] = 24;
    a4[1] = 24;
    a2[8] = 0;
    if ( (_DWORD)v18 )
    {
      if ( qword_180051940 )
      {
        NotifyHighestPriorityRequestRecipient(v18);
      }
      else
      {
        GetPriorityListTReqCall();
        qword_180051950 = 0;
        lpMem = 0;
        ServerFree(v14);
        *a2 = -2;
      }
    }
    if ( !*a2 )
    {
      a2[6] = 0;
      *a5 = a4[2] + 60;
    }
    LeaveCriticalSection(&gPriorityListCritSec);
    TRACELogPrint(0x80002u, "TapiEpilogSync (tapiRequestMakeCall) exit, returning x%x", *a2);
  }
}

```

## disassembly

```asm
0x18002fc10  mov     [rsp+arg_0], rbx
0x18002fc15  mov     [rsp+arg_10], rbp
0x18002fc1a  push    rsi
0x18002fc1b  push    rdi
0x18002fc1c  push    r12
0x18002fc1e  push    r14
0x18002fc20  push    r15
0x18002fc22  sub     rsp, 20h
0x18002fc26  xor     r15d, r15d
0x18002fc29  mov     rbx, r9
0x18002fc2c  mov     esi, r8d
0x18002fc2f  mov     rdi, rdx
0x18002fc32  cmp     [rdx+1Ch], r15d
0x18002fc36  jz      short loc_18002FC9B
0x18002fc38  lea     rbp, gPriorityListCritSec
0x18002fc3f  mov     rcx, rbp; lpCriticalSection
0x18002fc42  call    cs:__imp_EnterCriticalSection
0x18002fc48  mov     rcx, cs:lpMem; lpMem
0x18002fc4f  test    rcx, rcx
0x18002fc52  jz      short loc_18002FC68
0x18002fc54  mov     rbx, [rcx+1E0h]
0x18002fc5b  call    ServerFree
0x18002fc60  mov     rcx, rbx
0x18002fc63  test    rbx, rbx
0x18002fc66  jnz     short loc_18002FC54
0x18002fc68  mov     rcx, rbp; lpCriticalSection
0x18002fc6b  mov     cs:qword_180051950, r15
0x18002fc72  mov     cs:lpMem, r15
0x18002fc79  call    cs:__imp_LeaveCriticalSection
0x18002fc7f  lea     rdx, aTrequestmakeca; "TRequestMakeCall: couldn't exec proxy, "...
0x18002fc86  mov     ecx, 10002h
0x18002fc8b  call    TRACELogPrint
0x18002fc90  mov     dword ptr [rdi], 0FFFFFFFEh
0x18002fc96  jmp     loc_18002FF5A
0x18002fc9b  mov     r8d, [rdx+8]
0x18002fc9f  mov     ecx, esi
0x18002fca1  mov     rdx, rbx
0x18002fca4  call    IsBadStringParam
0x18002fca9  test    eax, eax
0x18002fcab  jnz     loc_18002FF54
0x18002fcb1  mov     r8d, [rdi+0Ch]
0x18002fcb5  or      ebp, 0FFFFFFFFh
0x18002fcb8  cmp     r8d, ebp
0x18002fcbb  jz      short loc_18002FCCF
0x18002fcbd  mov     rdx, rbx
0x18002fcc0  mov     ecx, esi
0x18002fcc2  call    IsBadStringParam
0x18002fcc7  test    eax, eax
0x18002fcc9  jnz     loc_18002FF54
0x18002fccf  mov     r8d, [rdi+10h]
0x18002fcd3  cmp     r8d, ebp
0x18002fcd6  jz      short loc_18002FCEA
0x18002fcd8  mov     rdx, rbx
0x18002fcdb  mov     ecx, esi
0x18002fcdd  call    IsBadStringParam
0x18002fce2  test    eax, eax
0x18002fce4  jnz     loc_18002FF54
0x18002fcea  mov     r8d, [rdi+14h]
0x18002fcee  cmp     r8d, ebp
0x18002fcf1  jz      short loc_18002FD05
0x18002fcf3  mov     rdx, rbx
0x18002fcf6  mov     ecx, esi
0x18002fcf8  call    IsBadStringParam
0x18002fcfd  test    eax, eax
0x18002fcff  jnz     loc_18002FF54
0x18002fd05  cmp     [rdi+18h], esi
0x18002fd08  ja      loc_18002FF54
0x18002fd0e  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18002fd15  mov     edx, 8; dwFlags
0x18002fd1a  mov     r8d, 1E8h; dwBytes
0x18002fd20  call    cs:__imp_HeapAlloc
0x18002fd26  mov     rsi, rax
0x18002fd29  test    rax, rax
0x18002fd2c  jz      loc_18002FF54
0x18002fd32  mov     r14d, 40002h
0x18002fd38  lea     rdx, aRequest0xP; "Request:  0x%p"
0x18002fd3f  mov     ecx, r14d
0x18002fd42  mov     r8, rax
0x18002fd45  call    TRACELogPrint
0x18002fd4a  mov     r8d, [rdi+8]
0x18002fd4e  mov     edx, 0A0h; cbDest
0x18002fd53  add     r8, rbx; pszSrc
0x18002fd56  mov     rcx, rsi; pszDest
0x18002fd59  call    StringCbCopyW
0x18002fd5e  mov     r8, rsi
0x18002fd61  lea     rdx, aDestaddressLs; "   DestAddress: [%ls]"
0x18002fd68  mov     ecx, r14d
0x18002fd6b  call    TRACELogPrint
0x18002fd70  mov     r12d, 50h ; 'P'
0x18002fd76  cmp     [rdi+0Ch], ebp
0x18002fd79  jz      short loc_18002FDA6
0x18002fd7b  mov     r8d, [rdi+0Ch]
0x18002fd7f  lea     r11, [rsi+0A0h]
0x18002fd86  add     r8, rbx; pszSrc
0x18002fd89  mov     rcx, r11; pszDest
0x18002fd8c  mov     edx, r12d; cbDest
0x18002fd8f  call    StringCbCopyW
0x18002fd94  mov     r8, r11
0x18002fd97  lea     rdx, aAppnameLs; "   AppName: [%ls]"
0x18002fd9e  mov     ecx, r14d
0x18002fda1  call    TRACELogPrint
0x18002fda6  cmp     [rdi+10h], ebp
0x18002fda9  jz      short loc_18002FDD6
0x18002fdab  mov     r8d, [rdi+10h]
0x18002fdaf  lea     r11, [rsi+0F0h]
0x18002fdb6  add     r8, rbx; pszSrc
0x18002fdb9  mov     rcx, r11; pszDest
0x18002fdbc  mov     rdx, r12; cbDest
0x18002fdbf  call    StringCbCopyW
0x18002fdc4  mov     r8, r11
0x18002fdc7  lea     rdx, aCalledpartyLs; "   CalledParty: [%ls]"
0x18002fdce  mov     ecx, r14d
0x18002fdd1  call    TRACELogPrint
0x18002fdd6  cmp     [rdi+14h], ebp
0x18002fdd9  jz      short loc_18002FE08
0x18002fddb  mov     r8d, [rdi+14h]
0x18002fddf  lea     r11, [rsi+140h]
0x18002fde6  add     r8, rbx; pszSrc
0x18002fde9  mov     rcx, r11; pszDest
0x18002fdec  mov     edx, 0A0h; cbDest
0x18002fdf1  call    StringCbCopyW
0x18002fdf6  mov     r8, r11
0x18002fdf9  lea     rdx, aCommentLs; "   Comment: [%ls]"
0x18002fe00  mov     ecx, r14d
0x18002fe03  call    TRACELogPrint
0x18002fe08  lea     rbp, gPriorityListCritSec
0x18002fe0f  mov     rcx, rbp; lpCriticalSection
0x18002fe12  call    cs:__imp_EnterCriticalSection
0x18002fe18  mov     rax, cs:qword_180051950
0x18002fe1f  test    rax, rax
0x18002fe22  jz      short loc_18002FE30
0x18002fe24  mov     [rax+1E0h], rsi
0x18002fe2b  mov     ecx, r15d
0x18002fe2e  jmp     short loc_18002FE3C
0x18002fe30  mov     cs:lpMem, rsi
0x18002fe37  mov     ecx, 1
0x18002fe3c  mov     cs:qword_180051950, rsi
0x18002fe43  mov     r12d, 18h
0x18002fe49  mov     eax, [rdi+18h]
0x18002fe4c  mov     [rbx], eax
0x18002fe4e  mov     [rbx+8], r12d
0x18002fe52  mov     [rbx+4], r12d
0x18002fe56  mov     [rdi+20h], r15d
0x18002fe5a  test    ecx, ecx
0x18002fe5c  jz      loc_18002FF1F
0x18002fe62  cmp     cs:qword_180051940, r15
0x18002fe69  jz      short loc_18002FE75
0x18002fe6b  call    NotifyHighestPriorityRequestRecipient
0x18002fe70  jmp     loc_18002FF1F
0x18002fe75  lea     rcx, [rsp+48h+lpMem]
0x18002fe7a  mov     [rsp+48h+lpMem], r15
0x18002fe7f  call    GetPriorityListTReqCall
0x18002fe84  mov     r14, [rsp+48h+lpMem]
0x18002fe89  test    r14, r14
0x18002fe8c  jz      short loc_18002FF03
0x18002fe8e  cmp     [r14], r15w
0x18002fe92  jz      short loc_18002FF03
0x18002fe94  mov     eax, [rbx]
0x18002fe96  mov     [rbx+8], eax
0x18002fe99  mov     [rbx+4], eax
0x18002fe9c  mov     eax, [rdi+18h]
0x18002fe9f  cmp     eax, r12d
0x18002fea2  ja      short loc_18002FED6
0x18002fea4  mov     dword ptr [rdi], 0FFFFFFF0h
0x18002feaa  mov     rcx, rsi; lpMem
0x18002fead  mov     cs:qword_180051950, r15
0x18002feb4  mov     cs:lpMem, r15
0x18002febb  call    ServerFree
0x18002fec0  mov     rcx, rbp; lpCriticalSection
0x18002fec3  call    cs:__imp_LeaveCriticalSection
0x18002fec9  mov     rcx, r14; lpMem
0x18002fecc  call    ServerFree
0x18002fed1  jmp     loc_18002FF5A
0x18002fed6  mov     [rbx+14h], r12d
0x18002feda  lea     r8, [r14+2]; pszSrc
0x18002fede  add     eax, 0FFFFFFE8h
0x18002fee1  mov     [rbx+10h], eax
0x18002fee4  mov     dword ptr [rdi+20h], 1
0x18002feeb  mov     ecx, [rbx+14h]
0x18002feee  mov     edx, [rbx+10h]; cbDest
0x18002fef1  add     rcx, rbx; pszDest
0x18002fef4  call    StringCbCopyW
0x18002fef9  mov     rcx, r14; lpMem
0x18002fefc  call    ServerFree
0x18002ff01  jmp     short loc_18002FF1F
0x18002ff03  mov     rcx, rsi; lpMem
0x18002ff06  mov     cs:qword_180051950, r15
0x18002ff0d  mov     cs:lpMem, r15
0x18002ff14  call    ServerFree
0x18002ff19  mov     dword ptr [rdi], 0FFFFFFFEh
0x18002ff1f  cmp     [rdi], r15d
0x18002ff22  jnz     short loc_18002FF35
0x18002ff24  mov     rax, [rsp+48h+arg_20]
0x18002ff29  mov     [rdi+18h], r15d
0x18002ff2d  mov     ecx, [rbx+8]
0x18002ff30  add     ecx, 3Ch ; '<'
0x18002ff33  mov     [rax], ecx
0x18002ff35  mov     rcx, rbp; lpCriticalSection
0x18002ff38  call    cs:__imp_LeaveCriticalSection
0x18002ff3e  mov     r8d, [rdi]
0x18002ff41  lea     rdx, aTapiepilogsync; "TapiEpilogSync (tapiRequestMakeCall) ex"...
0x18002ff48  mov     ecx, 80002h
0x18002ff4d  call    TRACELogPrint
0x18002ff52  jmp     short loc_18002FF5A
0x18002ff54  mov     dword ptr [rdi], 0FFFFFFF0h
0x18002ff5a  mov     rbx, [rsp+48h+arg_0]
0x18002ff5f  mov     rbp, [rsp+48h+arg_10]
0x18002ff64  add     rsp, 20h
0x18002ff68  pop     r15
0x18002ff6a  pop     r14
0x18002ff6c  pop     r12
0x18002ff6e  pop     rdi
0x18002ff6f  pop     rsi
0x18002ff70  retn
```
