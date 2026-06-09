# GetClusterAccountToken

- ea: `0x1800280f8`
- end: `0x180028426`
- name: `GetClusterAccountToken`
- size: `814`
- prototype: `__int64 __fastcall(PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800284b4`

## callees

- `0x18001deb0`
- `0x180020de8`
- `0x1800280f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002837f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002837f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800282ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800282ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800283ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800283ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800281b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800281b6`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x1800283dd`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterResource` at `0x1800283dd`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18002832e`
- `ext-ms-win-cluster-clusapi-l1-1-0!ClusterResourceControl` at `0x18002832e`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18002820b`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenClusterNode` at `0x18002820b`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1800283fa`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseCluster` at `0x1800283fa`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1800283ce`
- `ext-ms-win-cluster-clusapi-l1-1-0!CloseClusterNode` at `0x1800283ce`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18002814b`
- `ext-ms-win-cluster-clusapi-l1-1-0!OpenCluster` at `0x18002814b`
- `ext-ms-win-cluster-resutils-l1-1-0!ResUtilGetCoreClusterResources` at `0x180028262`
- `ext-ms-win-cluster-resutils-l1-1-0!ResUtilGetCoreClusterResources` at `0x180028262`

## pseudocode

```c
__int64 __fastcall GetClusterAccountToken(PHANDLE phNewToken)
{
  struct _HCLUSTER *v2; // rdi
  DWORD v3; // eax
  DWORD LastError; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // rax
  struct _HNODE *v9; // r14
  _QWORD *v10; // rax
  __int64 v11; // rdx
  HRESOURCE phClusterNameResource; // [rsp+40h] [rbp-9h] BYREF
  DWORD nSize; // [rsp+48h] [rbp-1h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp+3h] BYREF
  HANDLE OutBuffer; // [rsp+50h] [rbp+7h] BYREF
  _QWORD InBuffer[2]; // [rsp+58h] [rbp+Fh] BYREF
  WCHAR Buffer[16]; // [rsp+68h] [rbp+1Fh] BYREF

  phClusterNameResource = 0;
  *phNewToken = 0;
  OutBuffer = 0;
  memset(InBuffer, 0, 12);
  BytesReturned = 0;
  nSize = 16;
  v2 = OpenCluster(0);
  if ( v2 )
  {
    if ( !GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_40;
      }
      v6 = 15;
      goto LABEL_12;
    }
    v9 = OpenClusterNode(v2, Buffer);
    if ( !v9 )
    {
      LastError = GetLastError();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_40;
      }
      v6 = 16;
LABEL_12:
      v5 = v8[2];
      v7 = LastError;
      goto LABEL_6;
    }
    LastError = ResUtilGetCoreClusterResources(v2, &phClusterNameResource, 0, 0);
    if ( LastError )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_39;
      }
      v11 = 17;
    }
    else if ( phClusterNameResource )
    {
      LODWORD(InBuffer[0]) = GetCurrentProcessId();
      *(_QWORD *)((char *)InBuffer + 4) = 14;
      LastError = ClusterResourceControl(
                    phClusterNameResource,
                    v9,
                    0x100016Du,
                    InBuffer,
                    0xCu,
                    &OutBuffer,
                    8u,
                    &BytesReturned);
      if ( LastError )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_39;
        }
        v11 = 19;
      }
      else
      {
        if ( DuplicateTokenEx(OutBuffer, 0x2000000u, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
          goto LABEL_39;
        LastError = GetLastError();
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_39;
        }
        v11 = 20;
      }
    }
    else
    {
      LastError = 1168;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_39;
      }
      v11 = 18;
    }
    WPP_SF_d(v10[2], v11, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids, LastError);
LABEL_39:
    CloseClusterNode(v9);
    goto LABEL_40;
  }
  v3 = GetLastError();
  LastError = v3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    v5 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v6 = 14;
    v7 = v3;
LABEL_6:
    WPP_SF_d(v5, v6, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids, v7);
  }
LABEL_40:
  if ( phClusterNameResource )
    CloseClusterResource(phClusterNameResource);
  if ( OutBuffer )
    CloseHandle(OutBuffer);
  if ( v2 )
    CloseCluster(v2);
  return LastError;
}

```

## disassembly

```asm
0x1800280f8  mov     [rsp-8+arg_8], rbx
0x1800280fd  mov     [rsp-8+arg_10], rsi
0x180028102  push    rbp
0x180028103  push    rdi
0x180028104  push    r14
0x180028106  lea     rbp, [rsp-47h]
0x18002810b  sub     rsp, 90h
0x180028112  mov     rax, cs:__security_cookie
0x180028119  xor     rax, rsp
0x18002811c  mov     [rbp+57h+var_18], rax
0x180028120  xor     eax, eax
0x180028122  mov     [rbp+57h+phClusterNameResource], 0
0x18002812a  mov     [rcx], rax
0x18002812d  mov     rsi, rcx
0x180028130  xor     ecx, ecx; lpszClusterName
0x180028132  mov     [rbp+57h+OutBuffer], 0
0x18002813a  mov     [rbp+57h+InBuffer], rax
0x18002813e  mov     [rbp+57h+var_40], eax
0x180028141  mov     [rbp+57h+BytesReturned], eax
0x180028144  mov     [rbp+57h+nSize], 10h
0x18002814b  call    cs:__imp_OpenCluster
0x180028151  mov     rdi, rax
0x180028154  test    rax, rax
0x180028157  jnz     short loc_1800281AC
0x180028159  call    cs:__imp_GetLastError
0x18002815f  mov     ebx, eax
0x180028161  mov     r10, cs:WPP_GLOBAL_Control
0x180028168  lea     rcx, WPP_GLOBAL_Control
0x18002816f  cmp     r10, rcx
0x180028172  jz      loc_1800283D4
0x180028178  test    dword ptr [r10+1Ch], 200h
0x180028180  jz      loc_1800283D4
0x180028186  cmp     byte ptr [r10+19h], 1
0x18002818b  jb      loc_1800283D4
0x180028191  mov     rcx, [r10+10h]
0x180028195  lea     edx, [rdi+0Eh]
0x180028198  mov     r9d, eax
0x18002819b  lea     r8, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids
0x1800281a2  call    WPP_SF_d
0x1800281a7  jmp     loc_1800283D4
0x1800281ac  lea     r8, [rbp+57h+nSize]; nSize
0x1800281b0  xor     ecx, ecx; NameType
0x1800281b2  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x1800281b6  call    cs:__imp_GetComputerNameExW
0x1800281bc  test    eax, eax
0x1800281be  jnz     short loc_180028204
0x1800281c0  call    cs:__imp_GetLastError
0x1800281c6  mov     ebx, eax
0x1800281c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800281cf  lea     rcx, WPP_GLOBAL_Control
0x1800281d6  cmp     rax, rcx
0x1800281d9  jz      loc_1800283D4
0x1800281df  test    dword ptr [rax+1Ch], 200h
0x1800281e6  jz      loc_1800283D4
0x1800281ec  cmp     byte ptr [rax+19h], 1
0x1800281f0  jb      loc_1800283D4
0x1800281f6  mov     edx, 0Fh
0x1800281fb  mov     rcx, [rax+10h]
0x1800281ff  mov     r9d, ebx
0x180028202  jmp     short loc_18002819B
0x180028204  lea     rdx, [rbp+57h+Buffer]; lpszNodeName
0x180028208  mov     rcx, rdi; hCluster
0x18002820b  call    cs:__imp_OpenClusterNode
0x180028211  mov     r14, rax
0x180028214  test    rax, rax
0x180028217  jnz     short loc_180028255
0x180028219  call    cs:__imp_GetLastError
0x18002821f  mov     ebx, eax
0x180028221  mov     rax, cs:WPP_GLOBAL_Control
0x180028228  lea     rcx, WPP_GLOBAL_Control
0x18002822f  cmp     rax, rcx
0x180028232  jz      loc_1800283D4
0x180028238  test    dword ptr [rax+1Ch], 200h
0x18002823f  jz      loc_1800283D4
0x180028245  cmp     byte ptr [rax+19h], 1
0x180028249  jb      loc_1800283D4
0x18002824f  lea     edx, [r14+10h]
0x180028253  jmp     short loc_1800281FB
0x180028255  xor     r9d, r9d; phClusterQuorumResource
0x180028258  lea     rdx, [rbp+57h+phClusterNameResource]; phClusterNameResource
0x18002825c  xor     r8d, r8d; phClusterIPAddressResource
0x18002825f  mov     rcx, rdi; hCluster
0x180028262  call    cs:__imp_ResUtilGetCoreClusterResources
0x180028268  mov     ebx, eax
0x18002826a  test    eax, eax
0x18002826c  jz      short loc_1800282A6
0x18002826e  mov     rax, cs:WPP_GLOBAL_Control
0x180028275  lea     rcx, WPP_GLOBAL_Control
0x18002827c  cmp     rax, rcx
0x18002827f  jz      loc_1800283CB
0x180028285  test    dword ptr [rax+1Ch], 200h
0x18002828c  jz      loc_1800283CB
0x180028292  cmp     byte ptr [rax+19h], 1
0x180028296  jb      loc_1800283CB
0x18002829c  mov     edx, 11h
0x1800282a1  jmp     loc_1800283B8
0x1800282a6  cmp     [rbp+57h+phClusterNameResource], 0
0x1800282ab  jnz     short loc_1800282EA
0x1800282ad  mov     ebx, 490h
0x1800282b2  mov     rax, cs:WPP_GLOBAL_Control
0x1800282b9  lea     rcx, WPP_GLOBAL_Control
0x1800282c0  cmp     rax, rcx
0x1800282c3  jz      loc_1800283CB
0x1800282c9  test    dword ptr [rax+1Ch], 200h
0x1800282d0  jz      loc_1800283CB
0x1800282d6  cmp     byte ptr [rax+19h], 1
0x1800282da  jb      loc_1800283CB
0x1800282e0  mov     edx, 12h
0x1800282e5  jmp     loc_1800283B8
0x1800282ea  call    cs:__imp_GetCurrentProcessId
0x1800282f0  mov     rcx, [rbp+57h+phClusterNameResource]; hResource
0x1800282f4  lea     r9, [rbp+57h+InBuffer]; lpInBuffer
0x1800282f8  mov     dword ptr [rbp+57h+InBuffer], eax
0x1800282fb  mov     r8d, 100016Dh; dwControlCode
0x180028301  lea     rax, [rbp+57h+BytesReturned]
0x180028305  mov     [rbp+57h+InBuffer+4], 0Eh
0x18002830d  mov     [rsp+0A0h+lpBytesReturned], rax; lpBytesReturned
0x180028312  mov     rdx, r14; hHostNode
0x180028315  lea     rax, [rbp+57h+OutBuffer]
0x180028319  mov     [rsp+0A0h+cbOutBufferSize], 8; cbOutBufferSize
0x180028321  mov     [rsp+0A0h+lpOutBuffer], rax; lpOutBuffer
0x180028326  mov     [rsp+0A0h+cbInBufferSize], 0Ch; cbInBufferSize
0x18002832e  call    cs:__imp_ClusterResourceControl
0x180028334  mov     ebx, eax
0x180028336  test    eax, eax
0x180028338  jz      short loc_180028363
0x18002833a  mov     rax, cs:WPP_GLOBAL_Control
0x180028341  lea     rcx, WPP_GLOBAL_Control
0x180028348  cmp     rax, rcx
0x18002834b  jz      short loc_1800283CB
0x18002834d  test    dword ptr [rax+1Ch], 200h
0x180028354  jz      short loc_1800283CB
0x180028356  cmp     byte ptr [rax+19h], 1
0x18002835a  jb      short loc_1800283CB
0x18002835c  mov     edx, 13h
0x180028361  jmp     short loc_1800283B8
0x180028363  mov     rcx, [rbp+57h+OutBuffer]; hExistingToken
0x180028367  mov     r9d, 2; ImpersonationLevel
0x18002836d  mov     [rsp+0A0h+lpOutBuffer], rsi; phNewToken
0x180028372  xor     r8d, r8d; lpTokenAttributes
0x180028375  mov     edx, 2000000h; dwDesiredAccess
0x18002837a  mov     [rsp+0A0h+cbInBufferSize], r9d; TokenType
0x18002837f  call    cs:__imp_DuplicateTokenEx
0x180028385  test    eax, eax
0x180028387  jnz     short loc_1800283CB
0x180028389  call    cs:__imp_GetLastError
0x18002838f  mov     ebx, eax
0x180028391  mov     rax, cs:WPP_GLOBAL_Control
0x180028398  lea     rcx, WPP_GLOBAL_Control
0x18002839f  cmp     rax, rcx
0x1800283a2  jz      short loc_1800283CB
0x1800283a4  test    dword ptr [rax+1Ch], 200h
0x1800283ab  jz      short loc_1800283CB
0x1800283ad  cmp     byte ptr [rax+19h], 1
0x1800283b1  jb      short loc_1800283CB
0x1800283b3  mov     edx, 14h
0x1800283b8  mov     rcx, [rax+10h]
0x1800283bc  lea     r8, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids
0x1800283c3  mov     r9d, ebx
0x1800283c6  call    WPP_SF_d
0x1800283cb  mov     rcx, r14; hNode
0x1800283ce  call    cs:__imp_CloseClusterNode
0x1800283d4  mov     rcx, [rbp+57h+phClusterNameResource]; hResource
0x1800283d8  test    rcx, rcx
0x1800283db  jz      short loc_1800283E3
0x1800283dd  call    cs:__imp_CloseClusterResource
0x1800283e3  mov     rcx, [rbp+57h+OutBuffer]; hObject
0x1800283e7  test    rcx, rcx
0x1800283ea  jz      short loc_1800283F2
0x1800283ec  call    cs:__imp_CloseHandle
0x1800283f2  test    rdi, rdi
0x1800283f5  jz      short loc_180028400
0x1800283f7  mov     rcx, rdi; hCluster
0x1800283fa  call    cs:__imp_CloseCluster
0x180028400  mov     eax, ebx
0x180028402  mov     rcx, [rbp+57h+var_18]
0x180028406  xor     rcx, rsp; StackCookie
0x180028409  call    __security_check_cookie
0x18002840e  lea     r11, [rsp+0A0h+var_10]
0x180028416  mov     rbx, [r11+28h]
0x18002841a  mov     rsi, [r11+30h]
0x18002841e  mov     rsp, r11
0x180028421  pop     r14
0x180028423  pop     rdi
0x180028424  pop     rbp
0x180028425  retn
```
