# P2PReadHeaderListToCopy(char const *,char const *,char * * &)

- ea: `0x180042730`
- end: `0x180042961`
- name: `?P2PReadHeaderListToCopy@@YAXPEBD0AEAPEAPEAD@Z`
- size: `561`
- prototype: `void __fastcall(const char *, const char *, char ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180041d5c`

## callees

- `0x180042730`
- `0x180043a00`
- `0x180072c70`
- `0x1800730dc`
- `0x18007310c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180042780`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180042780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042917`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042917`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800427bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180042823`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800427bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180042823`

## string_xrefs

- `0x18004276e`: `Software\Microsoft\Windows NT\CurrentVersion\PeerDist\Service\`

## pseudocode

```c
void __fastcall P2PReadHeaderListToCopy(const char *a1, const char *a2, char ***a3)
{
  char *pvData; // rbx
  char **v4; // rdi
  char *v5; // rax
  DWORD v6; // ecx
  int v7; // esi
  __int64 v8; // r8
  unsigned int v9; // esi
  unsigned __int64 v10; // rax
  char **v11; // rax
  __int64 v12; // rdx
  DWORD v13; // r9d
  unsigned int v14; // r8d
  __int64 v15; // rax
  HKEY hkey; // [rsp+68h] [rbp+28h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp+30h] BYREF
  int v18; // [rsp+74h] [rbp+34h]

  v18 = HIDWORD(a3);
  hkey = 0;
  pcbData = 0;
  pvData = 0;
  v4 = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "Software\\Microsoft\\Windows NT\\CurrentVersion\\PeerDist\\Service\\",
          0,
          0x20119u,
          &hkey) )
  {
    pcbData = 0;
    RegGetValueA(hkey, 0, "ExtraHeaders", 2u, 0, 0, &pcbData);
    if ( pcbData )
    {
      v5 = (char *)operator new[](pcbData + 1, (const struct std::nothrow_t *)&std::nothrow);
      pvData = v5;
      if ( v5 )
      {
        memset_0(v5, 0, pcbData + 1);
        if ( !RegGetValueA(hkey, 0, "ExtraHeaders", 2u, 0, pvData, &pcbData) )
        {
          v6 = pcbData;
          if ( pcbData > 1 )
          {
            v7 = 0;
            v8 = 0;
            if ( pcbData != 1 )
            {
              do
              {
                if ( pvData[v8] == 44 )
                {
                  pvData[v8] = 0;
                  ++v7;
                  v6 = pcbData;
                }
                v8 = (unsigned int)(v8 + 1);
              }
              while ( (unsigned int)v8 < v6 - 1 );
            }
            v9 = v7 + 1;
            v10 = 8LL * (v9 + 1);
            if ( !is_mul_ok(v9 + 1, 8u) )
              v10 = -1;
            v11 = (char **)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
            v4 = v11;
            if ( v11 )
            {
              memset_0(v11, 0, 8LL * (v9 + 1));
              v12 = 0;
              *v4 = pvData;
              v13 = pcbData;
              v14 = 1;
              if ( pcbData != 1 )
              {
                do
                {
                  if ( v14 >= v9 )
                    break;
                  if ( !pvData[v12] )
                  {
                    v15 = v14++;
                    v4[v15] = &pvData[(unsigned int)v12 + 1];
                    v13 = pcbData;
                  }
                  v12 = (unsigned int)(v12 + 1);
                }
                while ( (unsigned int)v12 < v13 - 1 );
              }
              if ( P2PHeaderListToCopy )
                P2PDeleteHeaderList(&P2PHeaderListToCopy);
              P2PHeaderListToCopy = v4;
              v4 = 0;
              pvData = 0;
            }
          }
        }
      }
    }
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( pvData )
    operator delete(pvData);
  if ( v4 )
  {
    operator delete(*v4);
    operator delete(v4);
  }
}

```

## disassembly

```asm
0x180042730  mov     r11, rsp
0x180042733  mov     [r11+8], rbx
0x180042737  mov     [r11+20h], rsi
0x18004273b  mov     [r11+18h], r8
0x18004273f  mov     [r11+10h], rdx
0x180042743  push    rbp
0x180042744  push    rdi
0x180042745  push    r14
0x180042747  mov     rbp, rsp
0x18004274a  sub     rsp, 40h
0x18004274e  lea     rax, [rbp+hkey]
0x180042752  mov     [rbp+hkey], 0
0x18004275a  mov     r9d, 20119h; samDesired
0x180042760  mov     [r11-38h], rax
0x180042764  xor     r8d, r8d; ulOptions
0x180042767  mov     [rbp+arg_10], 0
0x18004276e  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x180042775  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004277c  xor     ebx, ebx
0x18004277e  xor     edi, edi
0x180042780  call    cs:__imp_RegOpenKeyExA
0x180042787  nop     dword ptr [rax+rax+00h]
0x18004278c  test    eax, eax
0x18004278e  jnz     loc_18004290E
0x180042794  mov     rcx, [rbp+hkey]; hkey
0x180042798  lea     rax, [rbp+arg_10]
0x18004279c  mov     [rsp+40h+pcbData], rax; pcbData
0x1800427a1  lea     esi, [rbx+2]
0x1800427a4  mov     [rsp+40h+pvData], rbx; pvData
0x1800427a9  lea     r8, aExtraheaders; "ExtraHeaders"
0x1800427b0  mov     r9d, esi; dwFlags
0x1800427b3  mov     [rsp+40h+pdwType], rbx; pdwType
0x1800427b8  xor     edx, edx; lpSubKey
0x1800427ba  mov     [rbp+arg_10], ebx
0x1800427bd  call    cs:__imp_RegGetValueA
0x1800427c4  nop     dword ptr [rax+rax+00h]
0x1800427c9  mov     eax, [rbp+arg_10]
0x1800427cc  test    eax, eax
0x1800427ce  jz      loc_18004290E
0x1800427d4  lea     ecx, [rax+1]; unsigned __int64
0x1800427d7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800427de  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800427e3  mov     rbx, rax
0x1800427e6  test    rax, rax
0x1800427e9  jz      loc_18004290E
0x1800427ef  mov     r8d, [rbp+arg_10]
0x1800427f3  xor     edx, edx; Val
0x1800427f5  inc     r8d; Size
0x1800427f8  mov     rcx, rax; void *
0x1800427fb  call    memset_0
0x180042800  mov     rcx, [rbp+hkey]; hkey
0x180042804  lea     rax, [rbp+arg_10]
0x180042808  mov     [rsp+40h+pcbData], rax; pcbData
0x18004280d  lea     r8, aExtraheaders; "ExtraHeaders"
0x180042814  mov     [rsp+40h+pvData], rbx; pvData
0x180042819  mov     r9d, esi; dwFlags
0x18004281c  xor     edx, edx; lpSubKey
0x18004281e  mov     [rsp+40h+pdwType], rdi; pdwType
0x180042823  call    cs:__imp_RegGetValueA
0x18004282a  nop     dword ptr [rax+rax+00h]
0x18004282f  test    eax, eax
0x180042831  jnz     loc_18004290E
0x180042837  mov     ecx, [rbp+arg_10]
0x18004283a  cmp     ecx, 1
0x18004283d  jbe     loc_18004290E
0x180042843  xor     esi, esi
0x180042845  lea     eax, [rcx-1]
0x180042848  xor     r8d, r8d
0x18004284b  test    eax, eax
0x18004284d  jz      short loc_18004286A
0x18004284f  cmp     byte ptr [r8+rbx], 2Ch ; ','
0x180042854  jnz     short loc_18004285F
0x180042856  mov     [r8+rbx], dil
0x18004285a  inc     esi
0x18004285c  mov     ecx, [rbp+arg_10]
0x18004285f  inc     r8d
0x180042862  lea     eax, [rcx-1]
0x180042865  cmp     r8d, eax
0x180042868  jb      short loc_18004284F
0x18004286a  inc     esi
0x18004286c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180042873  mov     eax, 8
0x180042878  lea     r14d, [rsi+1]
0x18004287c  mul     r14
0x18004287f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180042886  cmovb   rax, rcx
0x18004288a  mov     rcx, rax; unsigned __int64
0x18004288d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180042892  mov     rdi, rax
0x180042895  test    rax, rax
0x180042898  jz      short loc_18004290E
0x18004289a  lea     r8, ds:0[r14*8]; Size
0x1800428a2  xor     edx, edx; Val
0x1800428a4  mov     rcx, rax; void *
0x1800428a7  call    memset_0
0x1800428ac  xor     edx, edx
0x1800428ae  mov     [rdi], rbx
0x1800428b1  mov     r9d, [rbp+arg_10]
0x1800428b5  lea     r8d, [rdx+1]
0x1800428b9  lea     ecx, [r9-1]
0x1800428bd  test    ecx, ecx
0x1800428bf  jz      short loc_1800428ED
0x1800428c1  cmp     r8d, esi
0x1800428c4  jnb     short loc_1800428ED
0x1800428c6  cmp     byte ptr [rdx+rbx], 0
0x1800428ca  mov     eax, edx
0x1800428cc  jnz     short loc_1800428E3
0x1800428ce  lea     rcx, [rbx+1]
0x1800428d2  add     rcx, rax
0x1800428d5  mov     eax, r8d
0x1800428d8  inc     r8d
0x1800428db  mov     [rdi+rax*8], rcx
0x1800428df  mov     r9d, [rbp+arg_10]
0x1800428e3  inc     edx
0x1800428e5  lea     eax, [r9-1]
0x1800428e9  cmp     edx, eax
0x1800428eb  jb      short loc_1800428C1
0x1800428ed  cmp     cs:?P2PHeaderListToCopy@@3PEAPEADEA, 0; char * * P2PHeaderListToCopy
0x1800428f5  jz      short loc_180042903
0x1800428f7  lea     rcx, ?P2PHeaderListToCopy@@3PEAPEADEA; char ***
0x1800428fe  call    ?P2PDeleteHeaderList@@YAXAEAPEAPEAD@Z; P2PDeleteHeaderList(char * * &)
0x180042903  mov     cs:?P2PHeaderListToCopy@@3PEAPEADEA, rdi; char * * P2PHeaderListToCopy
0x18004290a  xor     edi, edi
0x18004290c  xor     ebx, ebx
0x18004290e  mov     rcx, [rbp+hkey]; hKey
0x180042912  test    rcx, rcx
0x180042915  jz      short loc_18004292B
0x180042917  call    cs:__imp_RegCloseKey
0x18004291e  nop     dword ptr [rax+rax+00h]
0x180042923  mov     [rbp+hkey], 0
0x18004292b  test    rbx, rbx
0x18004292e  jz      short loc_180042938
0x180042930  mov     rcx, rbx; Block
0x180042933  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180042938  test    rdi, rdi
0x18004293b  jz      short loc_18004294D
0x18004293d  mov     rcx, [rdi]; Block
0x180042940  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180042945  mov     rcx, rdi; Block
0x180042948  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004294d  mov     rbx, [rsp+40h+arg_0]
0x180042952  mov     rsi, [rsp+40h+arg_18]
0x180042957  add     rsp, 40h
0x18004295b  pop     r14
0x18004295d  pop     rdi
0x18004295e  pop     rbp
0x18004295f  retn
```
