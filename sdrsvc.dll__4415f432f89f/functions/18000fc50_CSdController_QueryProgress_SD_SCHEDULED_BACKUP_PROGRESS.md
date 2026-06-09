# CSdController::QueryProgress(SD_SCHEDULED_BACKUP_PROGRESS *)

- ea: `0x18000fc50`
- end: `0x18000fd94`
- name: `?QueryProgress@CSdController@@UEAAJPEAUSD_SCHEDULED_BACKUP_PROGRESS@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct SD_SCHEDULED_BACKUP_PROGRESS *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18000fc50`
- `0x18001586c`
- `0x180015974`
- `0x18001bc1c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fd54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fd54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fcc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fcc7`

## pseudocode

```c
__int64 __fastcall CSdController::QueryProgress(CSdController *this, struct SD_SCHEDULED_BACKUP_PROGRESS *a2)
{
  GUID v4; // xmm6
  __int64 v5; // rcx
  struct SD_SCHEDULED_BACKUP_PROGRESS *v6; // rax
  int v7; // ecx
  int v8; // ecx
  unsigned int v9; // ebx
  __int128 v11; // [rsp+20h] [rbp-29h] BYREF
  __int64 v12; // [rsp+30h] [rbp-19h]
  int v13; // [rsp+38h] [rbp-11h] BYREF
  __int16 v14; // [rsp+3Ch] [rbp-Dh]
  __int16 v15; // [rsp+3Eh] [rbp-Bh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v13, "CSdController::QueryProgress", 0xA55u, 1u);
  v12 = 0;
  v11 = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    v15 = 2654;
    goto LABEL_15;
  }
  v4 = GUID_NULL;
  v5 = 32;
  v6 = a2;
  do
  {
    *(_BYTE *)v6 = 0;
    v6 = (struct SD_SCHEDULED_BACKUP_PROGRESS *)((char *)v6 + 1);
    --v5;
  }
  while ( v5 );
  v13 = 0;
  v14 = 2654;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v7 = *((_DWORD *)this + 27);
  if ( !v7 )
  {
    LODWORD(v11) = 0;
    goto LABEL_12;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v4 = (GUID)*((_OWORD *)this + 7);
    LODWORD(v11) = *((_DWORD *)this + 32) != 0 ? 5 : 1;
    goto LABEL_12;
  }
  if ( v8 != 1 )
  {
LABEL_12:
    *((_OWORD *)a2 + 1) = v11;
    *(GUID *)a2 = v4;
    *((_QWORD *)&v11 + 1) = 0;
    goto LABEL_13;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 17) + 64LL))(*((_QWORD *)this + 17), &v11);
  if ( v13 >= 0 )
  {
    v4 = (GUID)*((_OWORD *)this + 7);
    v14 = 2693;
    goto LABEL_12;
  }
  v15 = 2693;
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
LABEL_15:
  CleanupBackupProgressFields((struct SD_BACKUP_PROGRESS *)&v11);
  v9 = v13;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v13);
  return v9;
}

```

## disassembly

```asm
0x18000fc50  push    rbp
0x18000fc52  push    rbx
0x18000fc53  push    rsi
0x18000fc54  push    rdi
0x18000fc55  lea     rbp, [rsp-3Fh]
0x18000fc5a  sub     rsp, 88h
0x18000fc61  mov     rdi, rdx
0x18000fc64  movaps  [rsp+0A0h+var_30], xmm6
0x18000fc69  mov     rbx, rcx
0x18000fc6c  lea     rdx, aCsdcontrollerQ_1; "CSdController::QueryProgress"
0x18000fc73  lea     rcx, [rbp+57h+var_68]; this
0x18000fc77  mov     r9d, 1; unsigned __int16
0x18000fc7d  mov     r8d, 0A55h; unsigned __int16
0x18000fc83  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000fc88  xor     eax, eax
0x18000fc8a  xorps   xmm0, xmm0
0x18000fc8d  mov     [rbp+57h+var_70], rax
0x18000fc91  movups  [rbp+57h+var_80], xmm0
0x18000fc95  test    rdi, rdi
0x18000fc98  jz      loc_18000FD5C
0x18000fc9e  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18000fca5  lea     ecx, [rax+20h]
0x18000fca8  mov     rax, rdi
0x18000fcab  mov     byte ptr [rax], 0
0x18000fcae  inc     rax
0x18000fcb1  sub     rcx, 1
0x18000fcb5  jnz     short loc_18000FCAB
0x18000fcb7  mov     [rbp+57h+var_68], ecx
0x18000fcba  mov     eax, 0A5Eh
0x18000fcbf  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000fcc3  mov     [rbp+57h+var_64], ax
0x18000fcc7  call    cs:__imp_EnterCriticalSection
0x18000fccd  mov     ecx, [rbx+6Ch]
0x18000fcd0  test    ecx, ecx
0x18000fcd2  jz      short loc_18000FD29
0x18000fcd4  sub     ecx, 1
0x18000fcd7  jz      short loc_18000FD11
0x18000fcd9  cmp     ecx, 1
0x18000fcdc  jnz     short loc_18000FD30
0x18000fcde  mov     rcx, [rbx+88h]
0x18000fce5  lea     rdx, [rbp+57h+var_80]
0x18000fce9  mov     rax, [rcx]
0x18000fcec  mov     rax, [rax+40h]
0x18000fcf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcf5  mov     [rbp+57h+var_68], eax
0x18000fcf8  test    eax, eax
0x18000fcfa  mov     eax, 0A85h
0x18000fcff  jns     short loc_18000FD07
0x18000fd01  mov     [rbp+57h+var_62], ax
0x18000fd05  jmp     short loc_18000FD50
0x18000fd07  movups  xmm6, xmmword ptr [rbx+70h]
0x18000fd0b  mov     [rbp+57h+var_64], ax
0x18000fd0f  jmp     short loc_18000FD30
0x18000fd11  mov     eax, [rbx+80h]
0x18000fd17  movups  xmm6, xmmword ptr [rbx+70h]
0x18000fd1b  neg     eax
0x18000fd1d  sbb     ecx, ecx
0x18000fd1f  and     ecx, 4
0x18000fd22  inc     ecx
0x18000fd24  mov     dword ptr [rbp+57h+var_80], ecx
0x18000fd27  jmp     short loc_18000FD30
0x18000fd29  mov     dword ptr [rbp+57h+var_80], 0
0x18000fd30  mov     eax, dword ptr [rbp+57h+var_80]
0x18000fd33  mov     [rdi+10h], eax
0x18000fd36  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000fd39  mov     [rdi+14h], eax
0x18000fd3c  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18000fd40  mov     [rdi+18h], rax
0x18000fd44  movdqu  xmmword ptr [rdi], xmm6
0x18000fd48  mov     qword ptr [rbp+57h+var_80+8], 0
0x18000fd50  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000fd54  call    cs:__imp_LeaveCriticalSection
0x18000fd5a  jmp     short loc_18000FD6C
0x18000fd5c  mov     eax, 0A5Eh
0x18000fd61  mov     [rbp+57h+var_68], 80070057h
0x18000fd68  mov     [rbp+57h+var_62], ax
0x18000fd6c  lea     rcx, [rbp+57h+var_80]; struct SD_BACKUP_PROGRESS *
0x18000fd70  call    ?CleanupBackupProgressFields@@YAJPEAUSD_BACKUP_PROGRESS@@@Z; CleanupBackupProgressFields(SD_BACKUP_PROGRESS *)
0x18000fd75  mov     ebx, [rbp+57h+var_68]
0x18000fd78  lea     rcx, [rbp+57h+var_68]; this
0x18000fd7c  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000fd81  movaps  xmm6, [rsp+0A0h+var_30]
0x18000fd86  mov     eax, ebx
0x18000fd88  add     rsp, 88h
0x18000fd8f  pop     rdi
0x18000fd90  pop     rsi
0x18000fd91  pop     rbx
0x18000fd92  pop     rbp
0x18000fd93  retn
```
