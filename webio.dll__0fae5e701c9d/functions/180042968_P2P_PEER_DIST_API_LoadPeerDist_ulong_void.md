# P2P_PEER_DIST_API::LoadPeerDist(ulong *,void * *)

- ea: `0x180042968`
- end: `0x180042b5d`
- name: `?LoadPeerDist@P2P_PEER_DIST_API@@QEAAKPEAKPEAPEAX@Z`
- size: `501`
- prototype: `unsigned int __fastcall(P2P_PEER_DIST_API *__hidden this, unsigned int *, void **)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x180041d5c`

## callees

- `0x180042968`
- `0x180042b64`
- `0x180042b98`
- `0x180042c64`
- `0x180042d48`
- `0x180042e0c`
- `0x180042ed0`
- `0x180042f98`
- `0x180043064`
- `0x180043130`
- `0x1800431fc`
- `0x1800432c8`
- `0x180043394`
- `0x180043b24`
- `0x1800722f0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800429a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800429a1`

## string_xrefs

- `0x180042a94`: `ClientBlockRead`
- `0x180042a7b`: `ClientStreamRead`

## pseudocode

```c
__int64 __fastcall P2P_PEER_DIST_API::LoadPeerDist(P2P_PEER_DIST_API *this, unsigned int *a2, void **a3)
{
  DWORD PeerDistDLLPath; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  WCHAR LibFileName[264]; // [rsp+20h] [rbp-228h] BYREF

  PeerDistDLLPath = P2P_PEER_DIST_API::GetPeerDistDLLPath(this, LibFileName, (unsigned int)a3);
  if ( !PeerDistDLLPath )
  {
    hModule = LoadLibraryExW(LibFileName, 0, 0);
    if ( hModule )
    {
      PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(unsigned long,void * *,unsigned long *)>();
      if ( !PeerDistDLLPath )
      {
        PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *)>(v5, v4, &qword_1800AE618);
        if ( !PeerDistDLLPath )
        {
          PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,enum PEERDIST_STATUS *)>(
                              v7,
                              v6,
                              &qword_1800AE620);
          if ( !PeerDistDLLPath )
          {
            PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,void * *)>(
                                v9,
                                v8,
                                &qword_1800AE628);
            if ( !PeerDistDLLPath )
            {
              PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *)>(
                                  v11,
                                  v10,
                                  &qword_1800AE630);
              if ( !PeerDistDLLPath )
              {
                PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,unsigned long,unsigned char *,_OVERLAPPED *)>(
                                    v12,
                                    "ClientAddContentInformation",
                                    &qword_1800AE638);
                if ( !PeerDistDLLPath )
                {
                  PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,_OVERLAPPED *)>(
                                      v14,
                                      v13,
                                      &qword_1800AE640);
                  if ( !PeerDistDLLPath )
                  {
                    PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,unsigned long,unsigned char *,_OVERLAPPED *)>(
                                        v15,
                                        "ClientAddData",
                                        &qword_1800AE648);
                    if ( !PeerDistDLLPath )
                    {
                      PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,unsigned long,unsigned char *,unsigned long,_OVERLAPPED *)>(
                                          v16,
                                          "ClientStreamRead",
                                          &qword_1800AE650);
                      if ( !PeerDistDLLPath )
                      {
                        PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,unsigned long,unsigned char *,unsigned long,_OVERLAPPED *)>(
                                            v17,
                                            "ClientBlockRead",
                                            &qword_1800AE658);
                        if ( !PeerDistDLLPath )
                        {
                          PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,_OVERLAPPED *)>(
                                              v19,
                                              v18,
                                              &qword_1800AE660);
                          if ( !PeerDistDLLPath )
                          {
                            PeerDistDLLPath = P2pPeerDist(1, &P2pPeerDistHandle, &P2pVersion);
                            if ( !PeerDistDLLPath )
                            {
                              if ( P2pVersion <= 1 )
                                return 0;
                              PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,peerdist_status_info_tag *)>(
                                                  v21,
                                                  v20,
                                                  &qword_1800AE670);
                              if ( !PeerDistDLLPath )
                              {
                                PeerDistDLLPath = P2P_PEER_DIST_API::GetFunction<unsigned long (*)(void *,void *,enum _PEERDIST_CLIENT_INFO_BY_HANDLE_CLASS,unsigned long,void *)>(
                                                    v23,
                                                    v22,
                                                    &qword_1800AE668);
                                if ( !PeerDistDLLPath )
                                  return 0;
                              }
                              ((void (__fastcall *)(void *))qword_1800AE618)(P2pPeerDistHandle);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      PeerDistDLLPath = GetLastError();
      if ( !PeerDistDLLPath )
        return PeerDistDLLPath;
    }
  }
  P2P_PEER_DIST_API::UnloadPeerDist((P2P_PEER_DIST_API *)&P2pPeerDist);
  return PeerDistDLLPath;
}

```

## disassembly

```asm
0x180042968  push    rbx
0x18004296a  sub     rsp, 240h
0x180042971  mov     rax, cs:__security_cookie
0x180042978  xor     rax, rsp
0x18004297b  mov     [rsp+248h+var_18], rax
0x180042983  lea     rdx, [rsp+248h+LibFileName]; unsigned __int16 *
0x180042988  call    ?GetPeerDistDLLPath@P2P_PEER_DIST_API@@AEAAKPEAGI@Z; P2P_PEER_DIST_API::GetPeerDistDLLPath(ushort *,uint)
0x18004298d  mov     ebx, eax
0x18004298f  test    eax, eax
0x180042991  jnz     loc_180042B09
0x180042997  xor     r8d, r8d; dwFlags
0x18004299a  lea     rcx, [rsp+248h+LibFileName]; lpLibFileName
0x18004299f  xor     edx, edx; hFile
0x1800429a1  call    cs:__imp_LoadLibraryExW
0x1800429a8  nop     dword ptr [rax+rax+00h]
0x1800429ad  mov     cs:hModule, rax
0x1800429b4  test    rax, rax
0x1800429b7  jz      loc_180042B35
0x1800429bd  call    ??$GetFunction@P6AKKPEAPEAXPEAK@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKKPEAPEAXPEAK@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(ulong,void * *,ulong *)>(char const *,ulong (*&)(ulong,void * *,ulong *))
0x1800429c2  mov     ebx, eax
0x1800429c4  test    eax, eax
0x1800429c6  jnz     loc_180042B09
0x1800429cc  lea     r8, qword_1800AE618
0x1800429d3  call    ??$GetFunction@P6AKPEAX@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *)>(char const *,ulong (*&)(void *))
0x1800429d8  mov     ebx, eax
0x1800429da  test    eax, eax
0x1800429dc  jnz     loc_180042B09
0x1800429e2  lea     r8, qword_1800AE620
0x1800429e9  call    ??$GetFunction@P6AKPEAXPEAW4PEERDIST_STATUS@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAXPEAW4PEERDIST_STATUS@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,PEERDIST_STATUS *)>(char const *,ulong (*&)(void *,PEERDIST_STATUS *))
0x1800429ee  mov     ebx, eax
0x1800429f0  test    eax, eax
0x1800429f2  jnz     loc_180042B09
0x1800429f8  lea     r8, qword_1800AE628
0x1800429ff  call    ??$GetFunction@P6AKPEAXPEBUpeerdist_content_tag_tag@@0_KPEAPEAX@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAXPEBUpeerdist_content_tag_tag@@1_KPEAPEAX@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,void * *)>(char const *,ulong (*&)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,void * *))
0x180042a04  mov     ebx, eax
0x180042a06  test    eax, eax
0x180042a08  jnz     loc_180042B09
0x180042a0e  lea     r8, qword_1800AE630
0x180042a15  call    ??$GetFunction@P6AKPEAX0@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *)>(char const *,ulong (*&)(void *,void *))
0x180042a1a  mov     ebx, eax
0x180042a1c  test    eax, eax
0x180042a1e  jnz     loc_180042B09
0x180042a24  lea     r8, qword_1800AE638
0x180042a2b  lea     rdx, aClientaddconte; "ClientAddContentInformation"
0x180042a32  call    ??$GetFunction@P6AKPEAX0KPEAEPEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1KPEAEPEAU_OVERLAPPED@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,ulong,uchar *,_OVERLAPPED *)>(char const *,ulong (*&)(void *,void *,ulong,uchar *,_OVERLAPPED *))
0x180042a37  mov     ebx, eax
0x180042a39  test    eax, eax
0x180042a3b  jnz     loc_180042B09
0x180042a41  lea     r8, qword_1800AE640
0x180042a48  call    ??$GetFunction@P6AKPEAX0PEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1PEAU_OVERLAPPED@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,_OVERLAPPED *)>(char const *,ulong (*&)(void *,void *,_OVERLAPPED *))
0x180042a4d  mov     ebx, eax
0x180042a4f  test    eax, eax
0x180042a51  jnz     loc_180042B09
0x180042a57  lea     r8, qword_1800AE648
0x180042a5e  lea     rdx, aClientadddata; "ClientAddData"
0x180042a65  call    ??$GetFunction@P6AKPEAX0KPEAEPEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1KPEAEPEAU_OVERLAPPED@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,ulong,uchar *,_OVERLAPPED *)>(char const *,ulong (*&)(void *,void *,ulong,uchar *,_OVERLAPPED *))
0x180042a6a  mov     ebx, eax
0x180042a6c  test    eax, eax
0x180042a6e  jnz     loc_180042B09
0x180042a74  lea     r8, qword_1800AE650
0x180042a7b  lea     rdx, aClientstreamre; "ClientStreamRead"
0x180042a82  call    ??$GetFunction@P6AKPEAX0KPEAEKPEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1KPEAEKPEAU_OVERLAPPED@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,ulong,uchar *,ulong,_OVERLAPPED *)>(char const *,ulong (*&)(void *,void *,ulong,uchar *,ulong,_OVERLAPPED *))
0x180042a87  mov     ebx, eax
0x180042a89  test    eax, eax
0x180042a8b  jnz     short loc_180042B09
0x180042a8d  lea     r8, qword_1800AE658
0x180042a94  lea     rdx, aClientblockrea; "ClientBlockRead"
0x180042a9b  call    ??$GetFunction@P6AKPEAX0KPEAEKPEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1KPEAEKPEAU_OVERLAPPED@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,ulong,uchar *,ulong,_OVERLAPPED *)>(char const *,ulong (*&)(void *,void *,ulong,uchar *,ulong,_OVERLAPPED *))
0x180042aa0  mov     ebx, eax
0x180042aa2  test    eax, eax
0x180042aa4  jnz     short loc_180042B09
0x180042aa6  lea     r8, qword_1800AE660
0x180042aad  call    ??$GetFunction@P6AKPEAXPEBUpeerdist_content_tag_tag@@0_KPEAU_OVERLAPPED@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAXPEBUpeerdist_content_tag_tag@@1_KPEAU_OVERLAPPED@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,_OVERLAPPED *)>(char const *,ulong (*&)(void *,peerdist_content_tag_tag const *,void *,unsigned __int64,_OVERLAPPED *))
0x180042ab2  mov     ebx, eax
0x180042ab4  test    eax, eax
0x180042ab6  jnz     short loc_180042B09
0x180042ab8  lea     ecx, [rax+1]
0x180042abb  mov     rax, cs:?P2pPeerDist@@3VP2P_PEER_DIST_API@@A; P2P_PEER_DIST_API P2pPeerDist
0x180042ac2  lea     r8, ?P2pVersion@@3KA; ulong P2pVersion
0x180042ac9  lea     rdx, ?P2pPeerDistHandle@@3PEAXEA; void * P2pPeerDistHandle
0x180042ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ad5  mov     ebx, eax
0x180042ad7  test    eax, eax
0x180042ad9  jnz     short loc_180042B09
0x180042adb  cmp     cs:?P2pVersion@@3KA, 1; ulong P2pVersion
0x180042ae2  jbe     short loc_180042B31
0x180042ae4  lea     r8, qword_1800AE670
0x180042aeb  call    ??$GetFunction@P6AKPEAXPEAUpeerdist_status_info_tag@@@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAXPEAUpeerdist_status_info_tag@@@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,peerdist_status_info_tag *)>(char const *,ulong (*&)(void *,peerdist_status_info_tag *))
0x180042af0  mov     ebx, eax
0x180042af2  test    eax, eax
0x180042af4  jz      short loc_180042B49
0x180042af6  mov     rcx, cs:?P2pPeerDistHandle@@3PEAXEA; void * P2pPeerDistHandle
0x180042afd  mov     rax, cs:qword_1800AE618
0x180042b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042b09  lea     rcx, ?P2pPeerDist@@3VP2P_PEER_DIST_API@@A; this
0x180042b10  call    ?UnloadPeerDist@P2P_PEER_DIST_API@@QEAAXXZ; P2P_PEER_DIST_API::UnloadPeerDist(void)
0x180042b15  mov     eax, ebx
0x180042b17  mov     rcx, [rsp+248h+var_18]
0x180042b1f  xor     rcx, rsp; StackCookie
0x180042b22  call    __security_check_cookie
0x180042b27  add     rsp, 240h
0x180042b2e  pop     rbx
0x180042b2f  retn
0x180042b31  xor     ebx, ebx
0x180042b33  jmp     short loc_180042B15
0x180042b35  call    cs:__imp_GetLastError
0x180042b3c  nop     dword ptr [rax+rax+00h]
0x180042b41  mov     ebx, eax
0x180042b43  test    eax, eax
0x180042b45  jz      short loc_180042B15
0x180042b47  jmp     short loc_180042B09
0x180042b49  lea     r8, qword_1800AE668
0x180042b50  call    ??$GetFunction@P6AKPEAX0W4_PEERDIST_CLIENT_INFO_BY_HANDLE_CLASS@@K0@Z@P2P_PEER_DIST_API@@AEAAKPEBDAEAP6AKPEAX1W4_PEERDIST_CLIENT_INFO_BY_HANDLE_CLASS@@K1@Z@Z; P2P_PEER_DIST_API::GetFunction<ulong (*)(void *,void *,_PEERDIST_CLIENT_INFO_BY_HANDLE_CLASS,ulong,void *)>(char const *,ulong (*&)(void *,void *,_PEERDIST_CLIENT_INFO_BY_HANDLE_CLASS,ulong,void *))
0x180042b55  mov     ebx, eax
0x180042b57  test    eax, eax
0x180042b59  jz      short loc_180042B31
0x180042b5b  jmp     short loc_180042AF6
```
