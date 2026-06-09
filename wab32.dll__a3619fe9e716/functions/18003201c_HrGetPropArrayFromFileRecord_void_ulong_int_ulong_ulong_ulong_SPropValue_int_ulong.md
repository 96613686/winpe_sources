# HrGetPropArrayFromFileRecord(void *,ulong,int *,ulong *,ulong *,ulong *,_SPropValue * *,int,ulong)

- ea: `0x18003201c`
- end: `0x1800321d0`
- name: `?HrGetPropArrayFromFileRecord@@YAJPEAXKPEAHPEAK22PEAPEAU_SPropValue@@HK@Z`
- size: `436`
- prototype: `__int64 __usercall@<rax>(HANDLE hFile@<rcx>, unsigned int@<edx>, int *@<r8>, unsigned int *@<r9>, unsigned int *, unsigned int *, struct _SPropValue **, int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032600`

## callees

- `0x180031a04`
- `0x18003201c`
- `0x180032588`
- `0x1800329b4`
- `0x180032bb4`
- `0x180033040`
- `0x180033ae0`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x180032114`
- `KERNEL32!SetFilePointer` at `0x180032114`
- `KERNEL32!LocalAlloc` at `0x1800320e9`
- `KERNEL32!LocalAlloc` at `0x1800320e9`
- `KERNEL32!GetFileSize` at `0x180032095`
- `KERNEL32!GetFileSize` at `0x180032095`
- `KERNEL32!ReadFile` at `0x180032136`
- `KERNEL32!ReadFile` at `0x180032136`

## pseudocode

```c
__int64 __fastcall HrGetPropArrayFromFileRecord(
        HANDLE hFile,
        unsigned int a2,
        int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6,
        struct _SPropValue **a7,
        int a8,
        unsigned int a9)
{
  int v13; // r8d
  DWORD FileSize; // eax
  int PropArrayFromBuffer; // ebx
  unsigned __int8 *v16; // rbx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-59h] BYREF
  void *v19; // [rsp+38h] [rbp-51h] BYREF
  _OWORD v20[2]; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v21[4]; // [rsp+60h] [rbp-29h] BYREF
  SIZE_T uBytes[2]; // [rsp+70h] [rbp-19h]

  NumberOfBytesRead = 0;
  v19 = 0;
  *(_OWORD *)v21 = 0;
  *(_OWORD *)uBytes = 0;
  if ( !ReadDataFromWABFile(hFile, a2, v21, 0x20u) )
    goto LABEL_15;
  if ( a4 )
    *a4 = v21[1];
  FileSize = GetFileSize(hFile, 0);
  v20[0] = *(_OWORD *)v21;
  v20[1] = *(_OWORD *)uBytes;
  if ( !(unsigned int)bIsValidRecord(v20, 0xFFFFFFFFLL, a2, FileSize, 1, a9) )
  {
    PropArrayFromBuffer = -2147221240;
    goto LABEL_17;
  }
  v19 = LocalAlloc(0x40u, HIDWORD(uBytes[1]));
  v16 = (unsigned __int8 *)v19;
  if ( !v19 )
  {
    PropArrayFromBuffer = -2147024882;
    goto LABEL_17;
  }
  if ( SetFilePointer(hFile, SHIDWORD(uBytes[0]), 0, 1u) == -1
    || !ReadFile(hFile, v19, HIDWORD(uBytes[1]), &NumberOfBytesRead, 0)
    || NumberOfBytesRead != HIDWORD(uBytes[1]) )
  {
    goto LABEL_15;
  }
  if ( !(unsigned int)SecurityCheckPropArrayBuffer(v16, HIDWORD(uBytes[1]), v21[3]) )
  {
    PropArrayFromBuffer = -2147221221;
    goto LABEL_17;
  }
  PropArrayFromBuffer = HrGetPropArrayFromBuffer(v16, HIDWORD(uBytes[1]), v21[3], 0, a7);
  if ( PropArrayFromBuffer >= 0 )
  {
    *a6 = v21[3];
LABEL_15:
    PropArrayFromBuffer = 0;
    if ( v21[1] == 3 )
      SetContainerObjectType(*a6, *a7, v13);
  }
LABEL_17:
  if ( a3 )
    *a3 = PropArrayFromBuffer == -2147221221;
  LocalFreeAndNull(&v19);
  return (unsigned int)PropArrayFromBuffer;
}

```

## disassembly

```asm
0x18003201c  push    rbp
0x18003201e  push    rbx
0x18003201f  push    rsi
0x180032020  push    rdi
0x180032021  push    r12
0x180032023  push    r14
0x180032025  push    r15
0x180032027  lea     rbp, [rsp-7]
0x18003202c  sub     rsp, 90h
0x180032033  mov     rax, cs:__security_cookie
0x18003203a  xor     rax, rsp
0x18003203d  mov     [rbp+37h+var_40], rax
0x180032041  mov     r14, [rbp+37h+arg_28]
0x180032045  xorps   xmm0, xmm0
0x180032048  mov     r15, [rbp+37h+arg_30]
0x18003204c  mov     rbx, r9
0x18003204f  mov     rsi, r8
0x180032052  mov     [rbp+37h+NumberOfBytesRead], 0
0x180032059  mov     r9d, 20h ; ' '; unsigned int
0x18003205f  mov     [rbp+37h+var_88], 0
0x180032067  lea     r8, [rbp+37h+var_60]; void *
0x18003206b  mov     r12d, edx
0x18003206e  movups  xmmword ptr [rbp+37h+var_60], xmm0
0x180032072  mov     rdi, rcx
0x180032075  movups  xmmword ptr [rbp+37h+uBytes], xmm0
0x180032079  call    ?ReadDataFromWABFile@@YAHPEAXK0K@Z; ReadDataFromWABFile(void *,ulong,void *,ulong)
0x18003207e  test    eax, eax
0x180032080  jz      loc_180032182
0x180032086  test    rbx, rbx
0x180032089  jz      short loc_180032090
0x18003208b  mov     eax, [rbp+37h+var_60+4]
0x18003208e  mov     [rbx], eax
0x180032090  xor     edx, edx; lpFileSizeHigh
0x180032092  mov     rcx, rdi; hFile
0x180032095  call    cs:__imp_GetFileSize
0x18003209b  mov     ecx, [rbp+37h+arg_40]
0x1800320a1  mov     r8d, r12d
0x1800320a4  movups  xmm0, xmmword ptr [rbp+37h+var_60]
0x1800320a8  mov     [rsp+0C0h+var_98], ecx
0x1800320ac  or      r12d, 0FFFFFFFFh
0x1800320b0  movups  xmm1, xmmword ptr [rbp+37h+uBytes]
0x1800320b4  mov     edx, r12d
0x1800320b7  mov     r9d, eax
0x1800320ba  lea     rcx, [rbp+37h+var_80]
0x1800320be  movaps  [rbp+37h+var_80], xmm0
0x1800320c2  movaps  [rbp+37h+var_70], xmm1
0x1800320c6  mov     dword ptr [rsp+0C0h+lpOverlapped], 1
0x1800320ce  call    ?bIsValidRecord@@YAHU_tagMPSWabRecordHeader@@KKKHK@Z; bIsValidRecord(_tagMPSWabRecordHeader,ulong,ulong,ulong,int,ulong)
0x1800320d3  test    eax, eax
0x1800320d5  jnz     short loc_1800320E1
0x1800320d7  mov     ebx, 80040108h
0x1800320dc  jmp     loc_180032195
0x1800320e1  mov     edx, dword ptr [rbp+37h+uBytes+0Ch]; uBytes
0x1800320e4  mov     ecx, 40h ; '@'; uFlags
0x1800320e9  call    cs:__imp_LocalAlloc
0x1800320ef  mov     [rbp+37h+var_88], rax
0x1800320f3  mov     rbx, rax
0x1800320f6  test    rax, rax
0x1800320f9  jnz     short loc_180032105
0x1800320fb  mov     ebx, 8007000Eh
0x180032100  jmp     loc_180032195
0x180032105  mov     edx, dword ptr [rbp+37h+uBytes+4]; lDistanceToMove
0x180032108  mov     r9d, 1; dwMoveMethod
0x18003210e  xor     r8d, r8d; lpDistanceToMoveHigh
0x180032111  mov     rcx, rdi; hFile
0x180032114  call    cs:__imp_SetFilePointer
0x18003211a  cmp     eax, r12d
0x18003211d  jz      short loc_180032182
0x18003211f  mov     r8d, dword ptr [rbp+37h+uBytes+0Ch]; nNumberOfBytesToRead
0x180032123  lea     r9, [rbp+37h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032127  mov     rdx, rbx; lpBuffer
0x18003212a  mov     [rsp+0C0h+lpOverlapped], 0; lpOverlapped
0x180032133  mov     rcx, rdi; hFile
0x180032136  call    cs:__imp_ReadFile
0x18003213c  test    eax, eax
0x18003213e  jz      short loc_180032182
0x180032140  mov     edx, dword ptr [rbp+37h+uBytes+0Ch]; unsigned int
0x180032143  cmp     [rbp+37h+NumberOfBytesRead], edx
0x180032146  jnz     short loc_180032182
0x180032148  mov     r8d, [rbp+37h+var_60+0Ch]; unsigned int
0x18003214c  mov     rcx, rbx; unsigned __int8 *
0x18003214f  call    ?SecurityCheckPropArrayBuffer@@YAHPEAEKK@Z; SecurityCheckPropArrayBuffer(uchar *,ulong,ulong)
0x180032154  test    eax, eax
0x180032156  jnz     short loc_18003215F
0x180032158  mov     ebx, 8004011Bh
0x18003215d  jmp     short loc_180032195
0x18003215f  mov     r8d, [rbp+37h+var_60+0Ch]; unsigned int
0x180032163  xor     r9d, r9d; unsigned int
0x180032166  mov     edx, dword ptr [rbp+37h+uBytes+0Ch]; unsigned int
0x180032169  mov     rcx, rbx; unsigned __int8 *
0x18003216c  mov     [rsp+0C0h+lpOverlapped], r15; struct _SPropValue **
0x180032171  call    ?HrGetPropArrayFromBuffer@@YAJPEAEKKKPEAPEAU_SPropValue@@@Z; HrGetPropArrayFromBuffer(uchar *,ulong,ulong,ulong,_SPropValue * *)
0x180032176  mov     ebx, eax
0x180032178  test    eax, eax
0x18003217a  js      short loc_180032195
0x18003217c  mov     eax, [rbp+37h+var_60+0Ch]
0x18003217f  mov     [r14], eax
0x180032182  xor     ebx, ebx
0x180032184  cmp     [rbp+37h+var_60+4], 3
0x180032188  jnz     short loc_180032195
0x18003218a  mov     rdx, [r15]; struct _SPropValue *
0x18003218d  mov     ecx, [r14]; unsigned int
0x180032190  call    ?SetContainerObjectType@@YAXKPEAU_SPropValue@@H@Z; SetContainerObjectType(ulong,_SPropValue *,int)
0x180032195  xor     eax, eax
0x180032197  cmp     ebx, 8004011Bh
0x18003219d  setz    al
0x1800321a0  test    rsi, rsi
0x1800321a3  jz      short loc_1800321A7
0x1800321a5  mov     [rsi], eax
0x1800321a7  lea     rcx, [rbp+37h+var_88]; void **
0x1800321ab  call    ?LocalFreeAndNull@@YAXPEAPEAX@Z; LocalFreeAndNull(void * *)
0x1800321b0  mov     eax, ebx
0x1800321b2  mov     rcx, [rbp+37h+var_40]
0x1800321b6  xor     rcx, rsp; StackCookie
0x1800321b9  call    __security_check_cookie
0x1800321be  add     rsp, 90h
0x1800321c5  pop     r15
0x1800321c7  pop     r14
0x1800321c9  pop     r12
0x1800321cb  pop     rdi
0x1800321cc  pop     rsi
0x1800321cd  pop     rbx
0x1800321ce  pop     rbp
0x1800321cf  retn
```
