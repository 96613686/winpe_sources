# Reachability_RemovePeer(AutoPtr<NtpPeer>,bool *,bool)

- ea: `0x18001bbe0`
- end: `0x18001bda1`
- name: `?Reachability_RemovePeer@@YAJV?$AutoPtr@UNtpPeer@@@@PEA_N_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x180022060`
- `0x180038000`
- `0x18003a900`

## callees

- `0x180014774`
- `0x180018138`
- `0x180018dfc`
- `0x18001abcc`
- `0x18001b810`
- `0x18001bbe0`
- `0x18001d9a0`
- `0x18002dbc4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bc7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bc7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bcf6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bc42`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bcf6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bd09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001bd09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bc0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Reachability_RemovePeer(volatile signed __int32 **a1, char *a2)
{
  __int64 v4; // rbp
  __int64 v5; // rsi
  _QWORD ***v6; // r9
  _QWORD **i; // rbx
  unsigned int v8; // ebx
  char v9; // si
  char v10; // bl
  volatile signed __int32 *v11; // rdx
  unsigned int v13; // edx
  NtpPeerGroupReachabilityInfo *v14; // rcx

  v4 = *((_QWORD *)*a1 + 1);
  v5 = *(_QWORD *)(v4 + 120);
  EnterCriticalSection((LPCRITICAL_SECTION)v5);
  if ( (unsigned __int8)FileLogAllowEntry(116) )
    FileLogAdd(L"Reachability:  removing peer %s.  ", *((_QWORD *)*a1 + 1) + 290LL);
  v6 = *(_QWORD ****)(v5 + 48);
  for ( i = *v6; ; i = (_QWORD **)*i )
  {
    if ( v6 == i )
      goto LABEL_5;
    if ( (unsigned int)AutoPtr<NtpPeer>::operator==(i + 2, a1) )
      break;
  }
  if ( v6 == i )
  {
LABEL_5:
    v8 = -2147418113;
LABEL_6:
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v4 + 120));
    goto LABEL_15;
  }
  *i[1] = *i;
  (*i)[1] = i[1];
  --*(_QWORD *)(v5 + 56);
  AutoPtr<NtpPeer>::`scalar deleting destructor'(i + 2);
  LocalFree(i);
  if ( *(_QWORD *)(v5 + 56) )
  {
    v9 = 1;
    v10 = 0;
  }
  else
  {
    if ( (unsigned __int8)FileLogAllowEntry(116) )
      FileLogAppend(L"LAST PEER IN GROUP!");
    v10 = 1;
    LeaveCriticalSection(*(LPCRITICAL_SECTION *)(v4 + 120));
    v9 = 0;
    DeleteCriticalSection(*(LPCRITICAL_SECTION *)(v4 + 120));
    v14 = *(NtpPeerGroupReachabilityInfo **)(v4 + 120);
    if ( v14 )
      NtpPeerGroupReachabilityInfo::`scalar deleting destructor'(v14, v13);
  }
  if ( (unsigned __int8)FileLogAllowEntry(116) )
    FileLogAppend(L"\n");
  if ( a2 )
    *a2 = v10;
  v8 = 0;
  if ( v9 )
    goto LABEL_6;
LABEL_15:
  v11 = *a1;
  if ( *a1 && _InterlockedExchangeAdd(v11, 0xFFFFFFFF) == 1 && *a1 )
    Ref<NtpPeer>::`scalar deleting destructor'(*a1, (unsigned int)v11);
  return v8;
}

```

## disassembly

```asm
0x18001bbe0  mov     [rsp+arg_8], rbx
0x18001bbe5  mov     [rsp+arg_10], rbp
0x18001bbea  mov     [rsp+arg_0], rcx
0x18001bbef  push    rsi
0x18001bbf0  push    rdi
0x18001bbf1  push    r14
0x18001bbf3  sub     rsp, 20h
0x18001bbf7  mov     r14, rdx
0x18001bbfa  mov     rdi, rcx
0x18001bbfd  mov     rax, [rcx]
0x18001bc00  mov     rbp, [rax+8]
0x18001bc04  mov     rsi, [rbp+78h]
0x18001bc08  mov     rcx, rsi; lpCriticalSection
0x18001bc0b  call    cs:__imp_EnterCriticalSection
0x18001bc12  nop     dword ptr [rax+rax+00h]
0x18001bc17  mov     ecx, 74h ; 't'
0x18001bc1c  call    FileLogAllowEntry
0x18001bc21  test    al, al
0x18001bc23  jnz     loc_18001BD3B
0x18001bc29  mov     r9, [rsi+30h]
0x18001bc2d  mov     rbx, [r9]
0x18001bc30  cmp     r9, rbx
0x18001bc33  jnz     loc_18001BD5A
0x18001bc39  mov     ebx, 8000FFFFh
0x18001bc3e  mov     rcx, [rbp+78h]; lpCriticalSection
0x18001bc42  call    cs:__imp_LeaveCriticalSection
0x18001bc49  nop     dword ptr [rax+rax+00h]
0x18001bc4e  jmp     short loc_18001BCB4
0x18001bc50  cmp     r9, rbx
0x18001bc53  jz      short loc_18001BC39
0x18001bc55  mov     rdx, [rbx+8]
0x18001bc59  mov     rax, [rbx]
0x18001bc5c  mov     [rdx], rax
0x18001bc5f  mov     rdx, [rbx]
0x18001bc62  mov     rax, [rbx+8]
0x18001bc66  mov     [rdx+8], rax
0x18001bc6a  dec     qword ptr [rsi+38h]
0x18001bc6e  lea     rcx, [rbx+10h]
0x18001bc72  call    ??_G?$AutoPtr@UNtpPeer@@@@QEAAPEAXI@Z; AutoPtr<NtpPeer>::`scalar deleting destructor'(uint)
0x18001bc77  mov     rcx, rbx; hMem
0x18001bc7a  call    cs:__imp_LocalFree
0x18001bc81  nop     dword ptr [rax+rax+00h]
0x18001bc86  cmp     qword ptr [rsi+38h], 0
0x18001bc8b  jz      short loc_18001BCDE
0x18001bc8d  mov     sil, 1
0x18001bc90  xor     bl, bl
0x18001bc92  mov     ecx, 74h ; 't'
0x18001bc97  call    FileLogAllowEntry
0x18001bc9c  test    al, al
0x18001bc9e  jnz     loc_18001BD87
0x18001bca4  test    r14, r14
0x18001bca7  jnz     loc_18001BD98
0x18001bcad  xor     ebx, ebx
0x18001bcaf  test    sil, sil
0x18001bcb2  jnz     short loc_18001BC3E
0x18001bcb4  mov     rdx, [rdi]
0x18001bcb7  test    rdx, rdx
0x18001bcba  jz      short loc_18001BCC8
0x18001bcbc  or      ecx, 0FFFFFFFFh
0x18001bcbf  lock xadd [rdx], ecx
0x18001bcc3  cmp     ecx, 1
0x18001bcc6  jz      short loc_18001BD2C
0x18001bcc8  mov     eax, ebx
0x18001bcca  mov     rbx, [rsp+38h+arg_8]
0x18001bccf  mov     rbp, [rsp+38h+arg_10]
0x18001bcd4  add     rsp, 20h
0x18001bcd8  pop     r14
0x18001bcda  pop     rdi
0x18001bcdb  pop     rsi
0x18001bcdc  retn
0x18001bcde  mov     ecx, 74h ; 't'
0x18001bce3  call    FileLogAllowEntry
0x18001bce8  test    al, al
0x18001bcea  jnz     loc_18001BD76
0x18001bcf0  mov     bl, 1
0x18001bcf2  mov     rcx, [rbp+78h]; lpCriticalSection
0x18001bcf6  call    cs:__imp_LeaveCriticalSection
0x18001bcfd  nop     dword ptr [rax+rax+00h]
0x18001bd02  xor     sil, sil
0x18001bd05  mov     rcx, [rbp+78h]; lpCriticalSection
0x18001bd09  call    cs:__imp_DeleteCriticalSection
0x18001bd10  nop     dword ptr [rax+rax+00h]
0x18001bd15  mov     rcx, [rbp+78h]; this
0x18001bd19  test    rcx, rcx
0x18001bd1c  jz      loc_18001BC92
0x18001bd22  call    ??_GNtpPeerGroupReachabilityInfo@@QEAAPEAXI@Z; NtpPeerGroupReachabilityInfo::`scalar deleting destructor'(uint)
0x18001bd27  jmp     loc_18001BC92
0x18001bd2c  mov     rcx, [rdi]; void *
0x18001bd2f  test    rcx, rcx
0x18001bd32  jz      short loc_18001BCC8
0x18001bd34  call    ??_G?$Ref@UNtpPeer@@@@QEAAPEAXI@Z; Ref<NtpPeer>::`scalar deleting destructor'(uint)
0x18001bd39  jmp     short loc_18001BCC8
0x18001bd3b  mov     rax, [rdi]
0x18001bd3e  mov     rdx, [rax+8]
0x18001bd42  add     rdx, 122h
0x18001bd49  lea     rcx, aReachabilityRe; "Reachability:  removing peer %s.  "
0x18001bd50  call    FileLogAdd
0x18001bd55  jmp     loc_18001BC29
0x18001bd5a  mov     rdx, rdi
0x18001bd5d  lea     rcx, [rbx+10h]
0x18001bd61  call    ??8?$AutoPtr@UNtpPeer@@@@QEAAHAEBV0@@Z; AutoPtr<NtpPeer>::operator==(AutoPtr<NtpPeer> const &)
0x18001bd66  test    eax, eax
0x18001bd68  jnz     loc_18001BC50
0x18001bd6e  mov     rbx, [rbx]
0x18001bd71  jmp     loc_18001BC30
0x18001bd76  lea     rcx, aLastPeerInGrou; "LAST PEER IN GROUP!"
0x18001bd7d  call    FileLogAppend
0x18001bd82  jmp     loc_18001BCF0
0x18001bd87  lea     rcx, asc_18007145C; "\n"
0x18001bd8e  call    FileLogAppend
0x18001bd93  jmp     loc_18001BCA4
0x18001bd98  mov     [r14], bl
0x18001bd9b  jmp     loc_18001BCAD
```
