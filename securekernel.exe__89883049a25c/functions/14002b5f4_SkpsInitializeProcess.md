# SkpsInitializeProcess

- ea: `0x14002b5f4`
- end: `0x14002b9ff`
- name: `SkpsInitializeProcess`
- size: `1035`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, size_t Size, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x1400010f0`
- `0x140002e40`
- `0x140002ef0`
- `0x14000e130`
- `0x14000e460`
- `0x14000f0f0`
- `0x14002b5f4`
- `0x14002ba08`
- `0x14005bb3c`
- `0x140063694`
- `0x140063720`
- `0x140099500`
- `0x1400a0fa0`
- `0x1400a1950`
- `0x1400ad564`
- `0x1400aeeec`
- `0x1400b17a4`
- `0x1400b1edc`
- `0x1400b1f70`
- `0x1400bb42c`
- `0x1400f9780`

## import_xrefs

- `skci!SkciCompareSigningLevels` at `0x14002b8e4`
- `skci!SkciCompareSigningLevels` at `0x14002b8e4`
- `cng!BCryptGenRandom` at `0x14002b751`
- `cng!BCryptGenRandom` at `0x14002b751`

## string_xrefs

- `0x14002b888`: `Unable to read Policy Metadata with error 0x%x.\n`

## pseudocode

```c
__int64 __fastcall SkpsInitializeProcess(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        _QWORD *Src,
        size_t Size,
        bool *a8)
{
  __int64 v8; // rsi
  __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // r8
  volatile signed __int32 *v15; // rdi
  int SecureImageInfo; // ebx
  size_t v17; // rbx
  _QWORD *Pool; // rax
  _QWORD *v19; // rsi
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // rbp
  int HandleTable; // eax
  int v24; // eax
  __int64 v25; // rdx
  int PolicyMetadata; // eax
  int Peb; // eax
  __int64 v28; // rdx
  char v29; // al
  _QWORD *v30; // rcx
  __int64 v31; // r8
  char v32; // r8
  __int64 v33; // rdx
  volatile signed __int32 *v34; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v35[16]; // [rsp+38h] [rbp-50h] BYREF
  __int128 v36; // [rsp+48h] [rbp-40h]
  __int64 v37; // [rsp+98h] [rbp+10h] BYREF

  v34 = 0;
  v8 = 0;
  v37 = 0;
  v36 = 0;
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFEFFFELL )
  {
    result = SkobReferenceObjectByHandle(a1, 0, 1, (__int64)&SkpsProcessType, &v34, 0);
    if ( (int)result < 0 )
      return result;
    v15 = v34;
    if ( _interlockedbittestandset(v34, 0) )
    {
      SecureImageInfo = -1073741269;
      goto LABEL_46;
    }
    SkobReferenceObject((__int64)v15);
    *((_QWORD *)v15 + 7) = a3;
    v17 = Size;
    if ( Size < 0x18 )
    {
      if ( Size < 8 )
      {
LABEL_14:
        SecureImageInfo = BCryptGenRandom(0, (PUCHAR)v15 + 440, 0x10u, 2u);
        if ( SecureImageInfo < 0 )
          goto LABEL_46;
LABEL_15:
        SecureImageInfo = SkobReferenceObjectByHandle(a5, 0, 1, (__int64)&SkmiImageType, (_QWORD *)v15 + 21, 0);
        if ( SecureImageInfo < 0
          || (SecureImageInfo = SkmmGetSecureImageInfo(*((_QWORD *)v15 + 21), v35), SecureImageInfo < 0) )
        {
LABEL_46:
          if ( (Microsoft_Windows_IsolatedUserModeEnableBits & 2) != 0 )
            McTemplateK0xqq_EtwWriteTransfer(
              v13,
              (unsigned int)IumProcessStartFailed,
              v14,
              *((_QWORD *)v15 + 54),
              *((_DWORD *)v15 + 14),
              SecureImageInfo);
          SkeCompleteProcessInitialization(v15, (unsigned int)SecureImageInfo, v14);
LABEL_49:
          SkobDereferenceObject((__int64)v15);
          return (unsigned int)SecureImageInfo;
        }
        *((_BYTE *)v15 + 280) = BYTE12(v36);
        v22 = SkiAttachProcess(v15);
        HandleTable = SkobCreateHandleTable(0);
        SecureImageInfo = HandleTable;
        if ( HandleTable < 0 )
        {
          DbgPrint("Handle table creation failed with error 0x%x.\n", (unsigned int)HandleTable);
          goto LABEL_43;
        }
        v24 = SkmmInitializeProcessAddressSpace(v15, a4);
        SecureImageInfo = v24;
        if ( v24 < 0 )
        {
          DbgPrint("Process Exe mapping failed with error 0x%x.\n", (unsigned int)v24);
          goto LABEL_43;
        }
        if ( !v8 )
        {
          *((_QWORD *)v15 + 58) = v15 + 114;
          *((_QWORD *)v15 + 57) = v15 + 114;
        }
        v25 = *(_QWORD *)(PsIumSystemProcess + 168);
        if ( !v25 )
        {
          SecureImageInfo = -1073741790;
          goto LABEL_43;
        }
        if ( v15 != (volatile signed __int32 *)1 && (*v15 & 0x1600) == 0 )
        {
          SecureImageInfo = SkmmMapSystemDll(v15, v25, qword_14016A018, qword_14016A020);
          if ( SecureImageInfo < 0 )
            goto LABEL_43;
          SecureImageInfo = SkpspPrepareSystemDllInitBlock();
          if ( SecureImageInfo < 0 )
            goto LABEL_43;
          PolicyMetadata = SkpsReadPolicyMetadata((__int64)v15);
          SecureImageInfo = PolicyMetadata;
          if ( PolicyMetadata < 0 )
          {
            DbgPrint("Unable to read Policy Metadata with error 0x%x.\n", (unsigned int)PolicyMetadata);
            goto LABEL_43;
          }
          Peb = SkpspCreatePeb(v15, a2);
          SecureImageInfo = Peb;
          if ( Peb < 0 )
          {
            DbgPrint("Peb creation failed with error 0x%x.\n", (unsigned int)Peb);
            goto LABEL_43;
          }
          *((_QWORD *)v15 + 37) = v15 + 72;
          *((_QWORD *)v15 + 36) = v15 + 72;
          *((_QWORD *)v15 + 38) = 0;
          *((_QWORD *)v15 + 39) = 0;
          if ( (v15[100] & 0x20) == 0 )
          {
            LOBYTE(v13) = *((_BYTE *)v15 + 280);
            LOBYTE(v28) = 12;
            if ( (unsigned int)SkciCompareSigningLevels(v13, v28) && (v15[100] & 0x40) != 0 )
              *((_BYTE *)v15 + 280) = 8;
            SkWriteProcessStartEvent(v15, 0);
            v29 = SkAcquireSpinLockExclusive(&SkpsProcessListLock);
            v30 = (_QWORD *)qword_14014DD18;
            LOBYTE(v31) = v29;
            if ( *(__int64 **)qword_14014DD18 != &SkpsProcessList )
              __fastfail(3u);
            SecureImageInfo = 0;
            *((_QWORD *)v15 + 31) = &SkpsProcessList;
            *((_QWORD *)v15 + 32) = v30;
            *v30 = v15 + 62;
            qword_14014DD18 = (__int64)(v15 + 62);
            SkeCompleteProcessInitialization(v15, 0, v31);
            LOBYTE(v33) = v32;
            SkReleaseSpinLockExclusive(&SkpsProcessListLock, v33);
            LODWORD(v13) = (_DWORD)a8;
            if ( a8 )
              *a8 = v8 != 0;
LABEL_43:
            if ( v22 )
              SkiAttachProcess(v22);
            if ( SecureImageInfo >= 0 )
              goto LABEL_49;
            goto LABEL_46;
          }
        }
        SecureImageInfo = -1073741637;
        goto LABEL_43;
      }
      *((_QWORD *)v15 + 54) = *Src;
    }
    else
    {
      Pool = (_QWORD *)SkAllocatePool(512, Size);
      v19 = Pool;
      if ( !Pool )
      {
        SecureImageInfo = -1073741670;
        goto LABEL_46;
      }
      memmove(Pool, Src, v17);
      *((_QWORD *)v15 + 34) = v19;
      *((_DWORD *)v15 + 66) = v17;
      *((_QWORD *)v15 + 54) = *v19;
      v21 = SkpsQueryProcessAttribute(v15, (unsigned int)TrustletType_TrustedApp, v20, &v37, 8);
      v8 = v37;
      if ( v21 >= 0 )
      {
        if ( v37 )
        {
          SecureImageInfo = -1073741637;
          goto LABEL_46;
        }
        goto LABEL_14;
      }
    }
    if ( v8 )
      goto LABEL_15;
    goto LABEL_14;
  }
  DbgPrint("Invalid PEB address.\n");
  return 3221225485LL;
}

```

## disassembly

```asm
0x14002b5f4  mov     r11, rsp
0x14002b5f7  mov     [r11+8], rbx
0x14002b5fb  mov     [r11+18h], rbp
0x14002b5ff  push    rsi
0x14002b600  push    rdi
0x14002b601  push    r12
0x14002b603  push    r14
0x14002b605  push    r15
0x14002b607  sub     rsp, 60h
0x14002b60b  lea     rax, [rdx-1]
0x14002b60f  mov     qword ptr [r11-58h], 0
0x14002b617  xor     esi, esi
0x14002b619  mov     r15, rdx
0x14002b61c  mov     rdx, 7FFFFFFEFFFEh
0x14002b626  mov     [r11+10h], rsi
0x14002b62a  xorps   xmm0, xmm0
0x14002b62d  mov     r12, r9
0x14002b630  mov     rbx, r8
0x14002b633  movups  [rsp+88h+var_40], xmm0
0x14002b638  cmp     rax, rdx
0x14002b63b  ja      loc_14002B9D4
0x14002b641  lea     rax, [r11-58h]
0x14002b645  mov     [r11-60h], rsi
0x14002b649  lea     r9, SkpsProcessType
0x14002b650  mov     [r11-68h], rax
0x14002b654  mov     r8b, 1
0x14002b657  xor     edx, edx
0x14002b659  call    SkobReferenceObjectByHandle
0x14002b65e  test    eax, eax
0x14002b660  js      loc_14002B9E5
0x14002b666  mov     rdi, [rsp+88h+var_58]
0x14002b66b  lock bts dword ptr [rdi], 0
0x14002b670  jnb     short loc_14002B67C
0x14002b672  mov     ebx, 0C000022Bh
0x14002b677  jmp     loc_14002B997
0x14002b67c  mov     rcx, rdi
0x14002b67f  call    SkobReferenceObject
0x14002b684  mov     [rdi+38h], rbx
0x14002b688  mov     rbx, [rsp+88h+Size]
0x14002b690  cmp     rbx, 18h
0x14002b694  jb      loc_14002B723
0x14002b69a  mov     r8d, 74744154h
0x14002b6a0  mov     rdx, rbx
0x14002b6a3  mov     ecx, 200h
0x14002b6a8  call    SkAllocatePool
0x14002b6ad  mov     rsi, rax
0x14002b6b0  test    rax, rax
0x14002b6b3  jnz     short loc_14002B6BF
0x14002b6b5  mov     ebx, 0C000009Ah
0x14002b6ba  jmp     loc_14002B997
0x14002b6bf  mov     rdx, [rsp+88h+Src]; Src
0x14002b6c7  mov     r8, rbx; Size
0x14002b6ca  mov     rcx, rsi; void *
0x14002b6cd  call    memmove
0x14002b6d2  mov     [rdi+110h], rsi
0x14002b6d9  lea     r9, [rsp+88h+arg_8]
0x14002b6e1  mov     [rdi+108h], ebx
0x14002b6e7  mov     rcx, rdi
0x14002b6ea  mov     rax, [rsi]
0x14002b6ed  mov     [rdi+1B0h], rax
0x14002b6f4  mov     edx, cs:TrustletType_TrustedApp
0x14002b6fa  mov     [rsp+88h+var_68], 8
0x14002b703  call    SkpsQueryProcessAttribute
0x14002b708  mov     rsi, [rsp+88h+arg_8]
0x14002b710  test    eax, eax
0x14002b712  js      short loc_14002B73B
0x14002b714  test    rsi, rsi
0x14002b717  jz      short loc_14002B740
0x14002b719  mov     ebx, 0C00000BBh
0x14002b71e  jmp     loc_14002B997
0x14002b723  cmp     rbx, 8
0x14002b727  jb      short loc_14002B740
0x14002b729  mov     rax, [rsp+88h+Src]
0x14002b731  mov     rcx, [rax]
0x14002b734  mov     [rdi+1B0h], rcx
0x14002b73b  test    rsi, rsi
0x14002b73e  jnz     short loc_14002B767
0x14002b740  xor     ecx, ecx; hAlgorithm
0x14002b742  lea     rdx, [rdi+1B8h]; pbBuffer
0x14002b749  lea     r9d, [rcx+2]; dwFlags
0x14002b74d  lea     r8d, [rcx+10h]; cbBuffer
0x14002b751  call    cs:__imp_BCryptGenRandom
0x14002b758  nop     dword ptr [rax+rax+00h]
0x14002b75d  mov     ebx, eax
0x14002b75f  test    eax, eax
0x14002b761  js      loc_14002B997
0x14002b767  mov     rcx, [rsp+88h+arg_20]
0x14002b76f  lea     r14, [rdi+0A8h]
0x14002b776  mov     [rsp+88h+var_60], 0
0x14002b77f  lea     r9, SkmiImageType
0x14002b786  mov     r8b, 1
0x14002b789  mov     [rsp+88h+var_68], r14
0x14002b78e  xor     edx, edx
0x14002b790  call    SkobReferenceObjectByHandle
0x14002b795  mov     ebx, eax
0x14002b797  test    eax, eax
0x14002b799  js      loc_14002B997
0x14002b79f  mov     rcx, [r14]
0x14002b7a2  lea     rdx, [rsp+88h+var_50]
0x14002b7a7  call    SkmmGetSecureImageInfo
0x14002b7ac  mov     ebx, eax
0x14002b7ae  test    eax, eax
0x14002b7b0  js      loc_14002B997
0x14002b7b6  mov     al, byte ptr [rsp+88h+var_40+0Ch]
0x14002b7ba  mov     rcx, rdi
0x14002b7bd  mov     [rdi+118h], al
0x14002b7c3  call    SkiAttachProcess
0x14002b7c8  xor     ecx, ecx
0x14002b7ca  mov     rbp, rax
0x14002b7cd  call    SkobCreateHandleTable
0x14002b7d2  mov     ebx, eax
0x14002b7d4  test    eax, eax
0x14002b7d6  jns     short loc_14002B7EB
0x14002b7d8  lea     rcx, aHandleTableCre; "Handle table creation failed with error"...
0x14002b7df  mov     edx, eax
0x14002b7e1  call    DbgPrint
0x14002b7e6  jmp     loc_14002B986
0x14002b7eb  mov     rdx, r12
0x14002b7ee  mov     rcx, rdi
0x14002b7f1  call    SkmmInitializeProcessAddressSpace
0x14002b7f6  mov     ebx, eax
0x14002b7f8  test    eax, eax
0x14002b7fa  jns     short loc_14002B805
0x14002b7fc  lea     rcx, aProcessExeMapp; "Process Exe mapping failed with error 0"...
0x14002b803  jmp     short loc_14002B7DF
0x14002b805  test    rsi, rsi
0x14002b808  jnz     short loc_14002B818
0x14002b80a  lea     rax, [rdi+1C8h]
0x14002b811  mov     [rax+8], rax
0x14002b815  mov     [rax], rax
0x14002b818  mov     rax, cs:PsIumSystemProcess
0x14002b81f  mov     rdx, [rax+0A8h]
0x14002b826  test    rdx, rdx
0x14002b829  jnz     short loc_14002B835
0x14002b82b  mov     ebx, 0C0000022h
0x14002b830  jmp     loc_14002B986
0x14002b835  cmp     rdi, 1
0x14002b839  jz      loc_14002B981
0x14002b83f  test    dword ptr [rdi], 1600h
0x14002b845  jnz     loc_14002B981
0x14002b84b  mov     r9, cs:qword_14016A020
0x14002b852  mov     rcx, rdi
0x14002b855  mov     r8, cs:qword_14016A018
0x14002b85c  call    SkmmMapSystemDll
0x14002b861  mov     ebx, eax
0x14002b863  test    eax, eax
0x14002b865  js      loc_14002B986
0x14002b86b  call    SkpspPrepareSystemDllInitBlock
0x14002b870  mov     ebx, eax
0x14002b872  test    eax, eax
0x14002b874  js      loc_14002B986
0x14002b87a  mov     rcx, rdi
0x14002b87d  call    SkpsReadPolicyMetadata
0x14002b882  mov     ebx, eax
0x14002b884  test    eax, eax
0x14002b886  jns     short loc_14002B894
0x14002b888  lea     rcx, aUnableToReadPo; "Unable to read Policy Metadata with err"...
0x14002b88f  jmp     loc_14002B7DF
0x14002b894  mov     rdx, r15
0x14002b897  mov     rcx, rdi
0x14002b89a  call    SkpspCreatePeb
0x14002b89f  mov     ebx, eax
0x14002b8a1  test    eax, eax
0x14002b8a3  jns     short loc_14002B8B1
0x14002b8a5  lea     rcx, aPebCreationFai; "Peb creation failed with error 0x%x.\n"
0x14002b8ac  jmp     loc_14002B7DF
0x14002b8b1  lea     rax, [rdi+120h]
0x14002b8b8  mov     [rax+8], rax
0x14002b8bc  mov     [rax], rax
0x14002b8bf  mov     qword ptr [rax+10h], 0
0x14002b8c7  mov     qword ptr [rax+18h], 0
0x14002b8cf  test    byte ptr [rdi+190h], 20h
0x14002b8d6  jnz     loc_14002B981
0x14002b8dc  mov     cl, [rdi+118h]
0x14002b8e2  mov     dl, 0Ch
0x14002b8e4  call    cs:__imp_SkciCompareSigningLevels
0x14002b8eb  nop     dword ptr [rax+rax+00h]
0x14002b8f0  test    eax, eax
0x14002b8f2  jz      short loc_14002B904
0x14002b8f4  test    byte ptr [rdi+190h], 40h
0x14002b8fb  jz      short loc_14002B904
0x14002b8fd  mov     byte ptr [rdi+118h], 8
0x14002b904  xor     edx, edx
0x14002b906  mov     rcx, rdi
0x14002b909  call    SkWriteProcessStartEvent
0x14002b90e  lea     rcx, SkpsProcessListLock
0x14002b915  call    SkAcquireSpinLockExclusive
0x14002b91a  mov     rcx, cs:qword_14014DD18
0x14002b921  lea     rdx, SkpsProcessList
0x14002b928  mov     r8b, al
0x14002b92b  cmp     [rcx], rdx
0x14002b92e  jz      short loc_14002B937
0x14002b930  mov     ecx, 3
0x14002b935  int     29h; Win8: RtlFailFast(ecx)
0x14002b937  lea     rax, [rdi+0F8h]
0x14002b93e  xor     ebx, ebx
0x14002b940  mov     [rax], rdx
0x14002b943  xor     edx, edx
0x14002b945  mov     [rax+8], rcx
0x14002b949  mov     [rcx], rax
0x14002b94c  mov     rcx, rdi
0x14002b94f  mov     cs:qword_14014DD18, rax
0x14002b956  call    SkeCompleteProcessInitialization
0x14002b95b  mov     dl, r8b
0x14002b95e  lea     rcx, SkpsProcessListLock
0x14002b965  call    SkReleaseSpinLockExclusive
0x14002b96a  mov     rcx, [rsp+88h+arg_38]
0x14002b972  test    rcx, rcx
0x14002b975  jz      short loc_14002B986
0x14002b977  test    rsi, rsi
0x14002b97a  setnz   al
0x14002b97d  mov     [rcx], al
0x14002b97f  jmp     short loc_14002B986
0x14002b981  mov     ebx, 0C00000BBh
0x14002b986  test    rbp, rbp
0x14002b989  jz      short loc_14002B993
0x14002b98b  mov     rcx, rbp
0x14002b98e  call    SkiAttachProcess
0x14002b993  test    ebx, ebx
0x14002b995  jns     short loc_14002B9C8
0x14002b997  test    byte ptr cs:Microsoft_Windows_IsolatedUserModeEnableBits, 2
0x14002b99e  jz      short loc_14002B9BE
0x14002b9a0  mov     eax, [rdi+38h]
0x14002b9a3  lea     rdx, IumProcessStartFailed
0x14002b9aa  mov     r9, [rdi+1B0h]
0x14002b9b1  mov     dword ptr [rsp+88h+var_60], ebx
0x14002b9b5  mov     dword ptr [rsp+88h+var_68], eax
0x14002b9b9  call    McTemplateK0xqq_EtwWriteTransfer
0x14002b9be  mov     edx, ebx
0x14002b9c0  mov     rcx, rdi
0x14002b9c3  call    SkeCompleteProcessInitialization
0x14002b9c8  mov     rcx, rdi
0x14002b9cb  call    SkobDereferenceObject
0x14002b9d0  mov     eax, ebx
0x14002b9d2  jmp     short loc_14002B9E5
0x14002b9d4  lea     rcx, aInvalidPebAddr; "Invalid PEB address.\n"
0x14002b9db  call    DbgPrint
0x14002b9e0  mov     eax, 0C000000Dh
0x14002b9e5  lea     r11, [rsp+88h+var_28]
0x14002b9ea  mov     rbx, [r11+30h]
0x14002b9ee  mov     rbp, [r11+40h]
0x14002b9f2  mov     rsp, r11
0x14002b9f5  pop     r15
0x14002b9f7  pop     r14
0x14002b9f9  pop     r12
0x14002b9fb  pop     rdi
0x14002b9fc  pop     rsi
0x14002b9fd  retn
```
