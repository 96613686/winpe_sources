# MgmDeleteGroupMembershipEntry

- ea: `0x180012800`
- end: `0x180012cdc`
- name: `MgmDeleteGroupMembershipEntry`
- size: `1244`
- prototype: `DWORD __stdcall(HANDLE hProtocol, DWORD dwSourceAddr, DWORD dwSourceMask, DWORD dwGroupAddr, DWORD dwGroupMask, DWORD dwIfIndex, DWORD dwIfNextHopIPAddr, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180012800`
- `0x180014bfc`
- `0x180014d2c`
- `0x180014f98`
- `0x180015040`
- `0x180015100`
- `0x180015178`
- `0x18001958c`
- `0x18001b548`
- `0x18001b588`
- `0x18001bb28`
- `0x18001bc4c`
- `0x18001d378`
- `0x18001d908`
- `0x18001de20`
- `0x18001de98`
- `0x18001f7e8`
- `0x18001f952`
- `0x18001f980`
- `0x180020010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x180012c1d`
- `rtutils!RouterLogEventA` at `0x180012c1d`

## string_xrefs

- `0x180012a40`: `IGMP join failed because owning protocol entry (%x, %x) not found`
- `0x18001289e`: `ENTERED MgmDeleteGroupMembership : Interface %x, %x : Source : %x, %x : Group : %x, %x`
- `0x180012c82`: `LEAVING MgmDeleteGroupMembership %x\n`

## pseudocode

```c
DWORD __stdcall MgmDeleteGroupMembershipEntry(
        HANDLE hProtocol,
        DWORD dwSourceAddr,
        DWORD dwSourceMask,
        DWORD dwGroupAddr,
        DWORD dwGroupMask,
        DWORD dwIfIndex,
        DWORD dwIfNextHopIPAddr,
        DWORD dwFlags)
{
  unsigned __int64 ProtocolEntry; // rdi
  DWORD v14; // ebx
  __int64 v15; // r14
  __int64 v16; // rbx
  int v17; // ecx
  int v18; // esi
  int v19; // r8d
  unsigned int *v20; // r11
  __int64 v21; // r15
  char *v22; // rbx
  __int64 GroupEntry; // rax
  __int64 v24; // r13
  __int64 SourceEntry; // rax
  __int64 v26; // r8
  LPSTR *plpszSubStringArray; // [rsp+20h] [rbp-E0h]
  int plpszSubStringArraya; // [rsp+20h] [rbp-E0h]
  __int64 dwErrorCode; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  DWORD v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v35[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v34 = 0;
  HIDWORD(v31) = dwSourceAddr;
  HIDWORD(v30) = dwSourceMask;
  LODWORD(v31) = dwGroupMask;
  v32 = dwIfIndex;
  LODWORD(v30) = dwIfNextHopIPAddr;
  memset_0(v35, 0, sizeof(v35));
  if ( !(unsigned int)EnterMgmAPI() )
    return 1003;
  if ( qword_18002B8A8 )
  {
    LOWORD(v34) = 0;
    FormatRRASErrorString(
      &v34,
      L"ENTERED MgmDeleteGroupMembership : Interface %x, %x : Source : %x, %x : Group : %x, %x",
      dwIfIndex,
      dwIfNextHopIPAddr,
      dwSourceAddr,
      dwSourceMask,
      dwGroupAddr,
      dwGroupMask,
      v30,
      v31,
      dwIfIndex);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v34);
  }
  AcquireReadLock(&qword_18002B9B8);
  ProtocolEntry = (unsigned __int64)hProtocol ^ 0x474D6300;
  v14 = VerifyProtocolHandle(ProtocolEntry);
  if ( !v14 )
  {
    v15 = 32LL * (dwIfIndex % dword_18002B92C);
    AcquireWriteLock((char *)qword_18002B9E8 + v15 + 16);
    v33 = 0;
    if ( (unsigned int)FindIfEntry((char *)qword_18002B9E8 + v15, dwIfIndex, dwIfNextHopIPAddr, &v33)
      && (v16 = v33) != 0 )
    {
      v17 = *(_DWORD *)(ProtocolEntry + 16);
      if ( *(_QWORD *)(v33 + 24) == *(_QWORD *)(ProtocolEntry + 16) )
      {
        if ( v17 != 10 )
        {
          v18 = 0;
LABEL_11:
          if ( (dwFlags & 1) != 0 )
          {
            DeleteInterfaceFromSourceEntry(
              ProtocolEntry,
              dwGroupAddr,
              v31,
              dwSourceAddr,
              HIDWORD(v30),
              dwIfIndex,
              v30,
              v18);
            DeleteSourceFromRefList(v16 + 40, dwSourceAddr, v19, dwGroupAddr, plpszSubStringArraya, v18);
            ReleaseWriteLock((char *)qword_18002B9E8 + v15 + 16);
            InvokeOutstandingCallbacks();
          }
          else
          {
            if ( (dwFlags & 2) != 0 && dwGroupAddr && dwSourceAddr )
            {
              v21 = 32LL * (dwGroupAddr % (dword_18002B930 - 1) + 1);
              AcquireReadLock((char *)qword_18002BA40 + v21 + 16);
              v22 = (char *)qword_18002BA40;
              GroupEntry = GetGroupEntry((char *)qword_18002BA40 + v21, dwGroupAddr);
              v24 = GroupEntry;
              if ( GroupEntry )
              {
                AcquireWriteLock(GroupEntry + 40);
                SourceEntry = GetSourceEntry(v24 + 16LL * (HIDWORD(v31) % (dword_18002B934 - 1) + 1) + 88, HIDWORD(v31));
                if ( SourceEntry )
                  DeleteInterfaceFromSourceMfe(
                    v24,
                    SourceEntry,
                    v32,
                    v30,
                    *(_DWORD *)(ProtocolEntry + 16),
                    *(_DWORD *)(ProtocolEntry + 20),
                    v18,
                    1);
                ReleaseWriteLock(v24 + 40);
                v22 = (char *)qword_18002BA40;
              }
              ReleaseReadLock(&v22[v21 + 16]);
            }
            ReleaseWriteLock((char *)qword_18002B9E8 + v15 + 16);
          }
          ReleaseReadLock(&qword_18002B9B8);
          v14 = 0;
          if ( !qword_18002B8A8 )
            goto LABEL_40;
          LOWORD(v34) = 0;
          v26 = 0;
          goto LABEL_39;
        }
        goto LABEL_15;
      }
      if ( v17 == 10 && *(__int16 *)(v33 + 32) < 0 )
      {
LABEL_15:
        v18 = 1;
        ProtocolEntry = GetProtocolEntry(&qword_18002B9A8, *(unsigned int *)(v33 + 24), *(unsigned int *)(v33 + 28));
        if ( ProtocolEntry )
          goto LABEL_11;
        if ( qword_18002B8A8 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"IGMP join failed because owning protocol entry (%x, %x) not found",
            *(unsigned int *)(v16 + 24),
            *v20);
          ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v34);
        }
        v14 = 1003;
        goto LABEL_36;
      }
      if ( qword_18002B8A8 )
      {
        LODWORD(dwErrorCode) = *(_DWORD *)(ProtocolEntry + 20);
        LODWORD(plpszSubStringArray) = *(_DWORD *)(ProtocolEntry + 16);
        LOWORD(v34) = 0;
        FormatRRASErrorString(
          &v34,
          L"Interface %x, %x is not owned by %x, %x",
          dwIfIndex,
          dwIfNextHopIPAddr,
          plpszSubStringArray,
          dwErrorCode);
        ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v34);
      }
      v14 = 87;
      if ( dword_18002BA54 )
        RouterLogEventA(qword_18002BA58, 1u, 0xC360u, 0, 0, 0x57u);
    }
    else
    {
      v14 = 1168;
      if ( qword_18002B8A8 )
        ((void (__fastcall *)(__int64, __int64, const wchar_t *))gMgmTemplateFunc)(
          gMgmEtwContext,
          qword_18002B8A8,
          L"Specified interface was not found");
    }
LABEL_36:
    ReleaseWriteLock((char *)qword_18002B9E8 + v15 + 16);
  }
  ReleaseReadLock(&qword_18002B9B8);
  if ( qword_18002B8A8 )
  {
    LOWORD(v34) = 0;
    v26 = v14;
LABEL_39:
    FormatRRASErrorString(&v34, L"LEAVING MgmDeleteGroupMembership %x\n", v26);
    ((void (__fastcall *)(__int64, __int64, int *))gMgmTemplateFunc)(gMgmEtwContext, qword_18002B8A8, &v34);
  }
LABEL_40:
  LeaveMgmWorker();
  return v14;
}

```

## disassembly

```asm
0x180012800  push    rbp
0x180012802  push    rbx
0x180012803  push    rsi
0x180012804  push    rdi
0x180012805  push    r12
0x180012807  push    r13
0x180012809  push    r14
0x18001280b  push    r15
0x18001280d  lea     rbp, [rsp-778h]
0x180012815  sub     rsp, 878h
0x18001281c  mov     rax, cs:__security_cookie
0x180012823  xor     rax, rsp
0x180012826  mov     [rbp+7B0h+var_50], rax
0x18001282d  mov     r14d, [rbp+7B0h+dwGroupMask]
0x180012834  mov     rdi, rcx
0x180012837  mov     r13d, [rbp+7B0h+dwIfIndex]
0x18001283e  xor     ecx, ecx
0x180012840  mov     esi, [rbp+7B0h+dwIfNextHopIPAddr]
0x180012846  mov     ebx, r8d
0x180012849  mov     [rsp+8B0h+var_850], ecx
0x18001284d  mov     r15d, edx
0x180012850  mov     [rsp+8B0h+var_864], edx
0x180012854  lea     rcx, [rsp+8B0h+var_84C]; void *
0x180012859  xor     edx, edx; Val
0x18001285b  mov     [rsp+8B0h+var_86C], ebx
0x18001285f  mov     r8d, 7FCh; Size
0x180012865  mov     [rsp+8B0h+var_868], r14d
0x18001286a  mov     r12d, r9d
0x18001286d  mov     [rsp+8B0h+var_860], r13d
0x180012872  mov     [rsp+8B0h+var_870], esi
0x180012876  call    memset_0
0x18001287b  call    EnterMgmAPI
0x180012880  xor     ecx, ecx
0x180012882  test    eax, eax
0x180012884  jnz     short loc_180012890
0x180012886  mov     eax, 3EBh
0x18001288b  jmp     loc_180012CB9
0x180012890  cmp     cs:qword_18002B8A8, rcx
0x180012897  jz      short loc_1800128E7
0x180012899  mov     [rsp+8B0h+var_878], r14d
0x18001289e  lea     rdx, aEnteredMgmdele; "ENTERED MgmDeleteGroupMembership : Inte"...
0x1800128a5  mov     [rsp+8B0h+var_880], r12d
0x1800128aa  mov     r9d, esi
0x1800128ad  mov     word ptr [rsp+8B0h+var_850], cx
0x1800128b2  mov     r8d, r13d
0x1800128b5  mov     dword ptr [rsp+8B0h+dwErrorCode], ebx
0x1800128b9  lea     rcx, [rsp+8B0h+var_850]
0x1800128be  mov     dword ptr [rsp+8B0h+plpszSubStringArray], r15d
0x1800128c3  call    FormatRRASErrorString
0x1800128c8  mov     rdx, cs:qword_18002B8A8
0x1800128cf  lea     r8, [rsp+8B0h+var_850]
0x1800128d4  mov     rcx, cs:gMgmEtwContext
0x1800128db  mov     rax, cs:gMgmTemplateFunc
0x1800128e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128e7  lea     rcx, qword_18002B9B8
0x1800128ee  call    AcquireReadLock
0x1800128f3  xor     rdi, 474D6300h
0x1800128fa  mov     rcx, rdi
0x1800128fd  call    VerifyProtocolHandle
0x180012902  mov     ebx, eax
0x180012904  test    eax, eax
0x180012906  jnz     loc_180012C63
0x18001290c  mov     rcx, cs:qword_18002B9E8
0x180012913  xor     edx, edx
0x180012915  mov     eax, r13d
0x180012918  add     rcx, 10h
0x18001291c  div     cs:dword_18002B92C
0x180012922  mov     r14d, edx
0x180012925  shl     r14, 5
0x180012929  add     rcx, r14
0x18001292c  call    AcquireWriteLock
0x180012931  mov     rcx, cs:qword_18002B9E8
0x180012938  lea     r9, [rsp+8B0h+var_858]
0x18001293d  add     rcx, r14
0x180012940  mov     [rsp+8B0h+var_858], 0
0x180012949  mov     r8d, esi
0x18001294c  mov     edx, r13d
0x18001294f  call    FindIfEntry
0x180012954  xor     r8d, r8d
0x180012957  test    eax, eax
0x180012959  jz      loc_180012C25
0x18001295f  mov     rbx, [rsp+8B0h+var_858]
0x180012964  test    rbx, rbx
0x180012967  jz      loc_180012C25
0x18001296d  mov     ecx, [rdi+10h]
0x180012970  lea     r11, [rbx+1Ch]
0x180012974  mov     edx, [rbx+18h]
0x180012977  cmp     edx, ecx
0x180012979  jnz     short loc_1800129FA
0x18001297b  mov     eax, [rdi+14h]
0x18001297e  cmp     [r11], eax
0x180012981  jnz     short loc_1800129FA
0x180012983  cmp     ecx, 0Ah
0x180012986  jz      loc_180012A0E
0x18001298c  mov     esi, r8d
0x18001298f  test    byte ptr [rbp+7B0h+dwFlags], 1
0x180012996  jz      loc_180012A81
0x18001299c  mov     r9d, [rsp+8B0h+var_870]
0x1800129a1  mov     edx, r12d
0x1800129a4  mov     eax, [rsp+8B0h+var_86C]
0x1800129a8  mov     rcx, rdi
0x1800129ab  mov     r8d, [rsp+8B0h+var_868]
0x1800129b0  mov     [rsp+8B0h+var_878], esi
0x1800129b4  mov     [rsp+8B0h+var_880], r9d
0x1800129b9  mov     r9d, r15d
0x1800129bc  mov     dword ptr [rsp+8B0h+dwErrorCode], r13d
0x1800129c1  mov     dword ptr [rsp+8B0h+plpszSubStringArray], eax
0x1800129c5  call    DeleteInterfaceFromSourceEntry
0x1800129ca  lea     rcx, [rbx+28h]
0x1800129ce  mov     dword ptr [rsp+8B0h+dwErrorCode], esi
0x1800129d2  mov     r9d, r12d
0x1800129d5  mov     edx, r15d
0x1800129d8  call    DeleteSourceFromRefList
0x1800129dd  mov     rcx, cs:qword_18002B9E8
0x1800129e4  add     rcx, 10h
0x1800129e8  add     rcx, r14
0x1800129eb  call    ReleaseWriteLock
0x1800129f0  call    InvokeOutstandingCallbacks
0x1800129f5  jmp     loc_180012B78
0x1800129fa  cmp     ecx, 0Ah
0x1800129fd  jnz     loc_180012BA0
0x180012a03  cmp     [rbx+20h], r8w
0x180012a08  jge     loc_180012BA0
0x180012a0e  mov     r8d, [r11]
0x180012a11  lea     rcx, qword_18002B9A8
0x180012a18  mov     esi, 1
0x180012a1d  call    GetProtocolEntry
0x180012a22  xor     r8d, r8d
0x180012a25  mov     rdi, rax
0x180012a28  test    rax, rax
0x180012a2b  jnz     loc_18001298F
0x180012a31  cmp     cs:qword_18002B8A8, r8
0x180012a38  jz      short loc_180012A77
0x180012a3a  mov     word ptr [rsp+8B0h+var_850], r8w
0x180012a40  lea     rdx, aIgmpJoinFailed; "IGMP join failed because owning protoco"...
0x180012a47  mov     r9d, [r11]
0x180012a4a  lea     rcx, [rsp+8B0h+var_850]
0x180012a4f  mov     r8d, [rbx+18h]
0x180012a53  call    FormatRRASErrorString
0x180012a58  mov     rdx, cs:qword_18002B8A8
0x180012a5f  lea     r8, [rsp+8B0h+var_850]
0x180012a64  mov     rcx, cs:gMgmEtwContext
0x180012a6b  mov     rax, cs:gMgmTemplateFunc
0x180012a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a77  mov     ebx, 3EBh
0x180012a7c  jmp     loc_180012C50
0x180012a81  test    byte ptr [rbp+7B0h+dwFlags], 2
0x180012a88  jz      loc_180012B65
0x180012a8e  test    r12d, r12d
0x180012a91  jz      loc_180012B65
0x180012a97  test    r15d, r15d
0x180012a9a  jz      loc_180012B65
0x180012aa0  mov     ecx, cs:dword_18002B930
0x180012aa6  xor     edx, edx
0x180012aa8  dec     ecx
0x180012aaa  mov     eax, r12d
0x180012aad  div     ecx
0x180012aaf  mov     rcx, cs:qword_18002BA40
0x180012ab6  add     rcx, 10h
0x180012aba  lea     r15d, [rdx+1]
0x180012abe  shl     r15, 5
0x180012ac2  add     rcx, r15
0x180012ac5  call    AcquireReadLock
0x180012aca  mov     rbx, cs:qword_18002BA40
0x180012ad1  mov     edx, r12d
0x180012ad4  lea     rcx, [r15+rbx]
0x180012ad8  call    GetGroupEntry
0x180012add  mov     r13, rax
0x180012ae0  test    rax, rax
0x180012ae3  jz      short loc_180012B59
0x180012ae5  lea     rcx, [rax+28h]
0x180012ae9  call    AcquireWriteLock
0x180012aee  mov     ecx, cs:dword_18002B934
0x180012af4  xor     edx, edx
0x180012af6  mov     eax, [rsp+8B0h+var_864]
0x180012afa  dec     ecx
0x180012afc  div     ecx
0x180012afe  lea     ecx, [rdx+1]
0x180012b01  mov     edx, [rsp+8B0h+var_864]
0x180012b05  shl     rcx, 4
0x180012b09  add     rcx, 58h ; 'X'
0x180012b0d  add     rcx, r13
0x180012b10  call    GetSourceEntry
0x180012b15  test    rax, rax
0x180012b18  jz      short loc_180012B49
0x180012b1a  mov     ecx, [rdi+14h]
0x180012b1d  mov     rdx, rax
0x180012b20  mov     r9d, [rsp+8B0h+var_870]
0x180012b25  mov     r8d, [rsp+8B0h+var_860]
0x180012b2a  mov     [rsp+8B0h+var_878], 1
0x180012b32  mov     [rsp+8B0h+var_880], esi
0x180012b36  mov     dword ptr [rsp+8B0h+dwErrorCode], ecx
0x180012b3a  mov     ecx, [rdi+10h]
0x180012b3d  mov     dword ptr [rsp+8B0h+plpszSubStringArray], ecx
0x180012b41  mov     rcx, r13
0x180012b44  call    DeleteInterfaceFromSourceMfe
0x180012b49  lea     rcx, [r13+28h]
0x180012b4d  call    ReleaseWriteLock
0x180012b52  mov     rbx, cs:qword_18002BA40
0x180012b59  lea     rcx, [r15+10h]
0x180012b5d  add     rcx, rbx
0x180012b60  call    ReleaseReadLock
0x180012b65  mov     rcx, cs:qword_18002B9E8
0x180012b6c  add     rcx, 10h
0x180012b70  add     rcx, r14
0x180012b73  call    ReleaseWriteLock
0x180012b78  lea     rcx, qword_18002B9B8
0x180012b7f  call    ReleaseReadLock
0x180012b84  xor     ebx, ebx
0x180012b86  cmp     cs:qword_18002B8A8, rbx
0x180012b8d  jz      loc_180012CB2
0x180012b93  mov     word ptr [rsp+8B0h+var_850], bx
0x180012b98  xor     r8d, r8d
0x180012b9b  jmp     loc_180012C82
0x180012ba0  cmp     cs:qword_18002B8A8, r8
0x180012ba7  jz      short loc_180012BF3
0x180012ba9  mov     eax, [rdi+14h]
0x180012bac  lea     rdx, aInterfaceXXIsN; "Interface %x, %x is not owned by %x, %x"
0x180012bb3  mov     dword ptr [rsp+8B0h+dwErrorCode], eax
0x180012bb7  mov     r9d, esi
0x180012bba  mov     dword ptr [rsp+8B0h+plpszSubStringArray], ecx
0x180012bbe  lea     rcx, [rsp+8B0h+var_850]
0x180012bc3  mov     word ptr [rsp+8B0h+var_850], r8w
0x180012bc9  mov     r8d, r13d
0x180012bcc  call    FormatRRASErrorString
0x180012bd1  mov     rdx, cs:qword_18002B8A8
0x180012bd8  lea     r8, [rsp+8B0h+var_850]
0x180012bdd  mov     rcx, cs:gMgmEtwContext
0x180012be4  mov     rax, cs:gMgmTemplateFunc
0x180012beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bf0  xor     r8d, r8d
0x180012bf3  cmp     cs:dword_18002BA54, 1
0x180012bfa  mov     ebx, 57h ; 'W'
0x180012bff  jb      short loc_180012C50
0x180012c01  mov     rcx, cs:qword_18002BA58; hLogHandle
0x180012c08  lea     edx, [rbx-56h]; dwEventType
0x180012c0b  mov     dword ptr [rsp+8B0h+dwErrorCode], ebx; dwErrorCode
0x180012c0f  xor     r9d, r9d; dwSubStringCount
0x180012c12  mov     [rsp+8B0h+plpszSubStringArray], r8; plpszSubStringArray
0x180012c17  mov     r8d, 0C360h; dwMessageId
0x180012c1d  call    cs:__imp_RouterLogEventA
0x180012c23  jmp     short loc_180012C50
0x180012c25  mov     rdx, cs:qword_18002B8A8
0x180012c2c  mov     ebx, 490h
0x180012c31  test    rdx, rdx
0x180012c34  jz      short loc_180012C50
0x180012c36  mov     rcx, cs:gMgmEtwContext
0x180012c3d  lea     r8, aSpecifiedInter; "Specified interface was not found"
0x180012c44  mov     rax, cs:gMgmTemplateFunc
0x180012c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c50  mov     rcx, cs:qword_18002B9E8
0x180012c57  add     rcx, 10h
0x180012c5b  add     rcx, r14
0x180012c5e  call    ReleaseWriteLock
0x180012c63  lea     rcx, qword_18002B9B8
0x180012c6a  call    ReleaseReadLock
0x180012c6f  xor     eax, eax
0x180012c71  cmp     cs:qword_18002B8A8, rax
0x180012c78  jz      short loc_180012CB2
0x180012c7a  mov     word ptr [rsp+8B0h+var_850], ax
0x180012c7f  mov     r8d, ebx
0x180012c82  lea     rdx, aLeavingMgmdele; "LEAVING MgmDeleteGroupMembership %x\n"
0x180012c89  lea     rcx, [rsp+8B0h+var_850]
0x180012c8e  call    FormatRRASErrorString
0x180012c93  mov     rdx, cs:qword_18002B8A8
0x180012c9a  lea     r8, [rsp+8B0h+var_850]
0x180012c9f  mov     rcx, cs:gMgmEtwContext
0x180012ca6  mov     rax, cs:gMgmTemplateFunc
0x180012cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb2  call    LeaveMgmWorker
0x180012cb7  mov     eax, ebx
0x180012cb9  mov     rcx, [rbp+7B0h+var_50]
0x180012cc0  xor     rcx, rsp; StackCookie
0x180012cc3  call    __security_check_cookie
0x180012cc8  add     rsp, 878h
0x180012ccf  pop     r15
0x180012cd1  pop     r14
0x180012cd3  pop     r13
0x180012cd5  pop     r12
0x180012cd7  pop     rdi
0x180012cd8  pop     rsi
0x180012cd9  pop     rbx
0x180012cda  pop     rbp
0x180012cdb  retn
```
