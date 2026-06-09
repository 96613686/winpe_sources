# NtQueryInformationThread

- ea: `0x1400addd0`
- end: `0x1400adfe0`
- name: `NtQueryInformationThread`
- size: `528`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x140002ef0`
- `0x14000e130`
- `0x140034154`
- `0x140042074`
- `0x1400a1950`
- `0x1400addd0`
- `0x1400b5a84`
- `0x1400d4e8c`
- `0x1400f0040`
- `0x1400f38f0`
- `0x1400fc554`

## pseudocode

```c
__int64 __fastcall NtQueryInformationThread(
        unsigned __int64 a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        __int64 a5)
{
  char v8; // r12
  _DWORD *StackBase; // rdi
  __int64 result; // rax
  int v11; // ebx
  int v12; // r14d
  int v13; // ebx
  int InformationThread; // eax
  __int64 v15; // r9
  int v16; // ebx
  _DWORD *v17; // [rsp+38h] [rbp-60h] BYREF
  _OWORD Src[3]; // [rsp+40h] [rbp-58h] BYREF
  unsigned __int64 v19; // [rsp+A0h] [rbp+8h] BYREF

  memset(Src, 0, 44);
  v19 = 0;
  v17 = 0;
  v8 = *((_BYTE *)KeGetPcr()->NtTib.StackBase + 96);
  if ( a1 == -2 )
  {
    v19 = -2;
    StackBase = KeGetPcr()->NtTib.StackBase;
    v17 = StackBase;
    SkobReferenceObject((__int64)StackBase);
  }
  else
  {
    result = SkobReferenceObjectByHandle(a1, v8, 0, (__int64)&SkeThreadType, &v17, &v19);
    if ( (int)result < 0 )
      return result;
    StackBase = v17;
  }
  switch ( a2 )
  {
    case 0u:
      v12 = 48;
      goto LABEL_14;
    case 0xCu:
      v12 = 4;
      goto LABEL_14;
    case 0x11u:
      v12 = 1;
      goto LABEL_14;
    case 0x17u:
      v12 = 16;
LABEL_14:
      v13 = a5;
      InformationThread = NkQueryInformationThread(v19, a2, a3, a4, a5);
      v11 = IumSanitizeReturnLength(v13, 4, v12, a4, InformationThread, 0);
      if ( v11 >= 0 && !a2 )
      {
        if ( a4 >= 0x30 )
        {
          LOBYTE(v19) = v8;
          if ( (unsigned __int8)SkAcquireRundownProtection(StackBase + 54) )
          {
            SkReleaseRundownProtection(v15, 0);
            v16 = 259;
          }
          else
          {
            v16 = StackBase[71];
          }
          if ( v8 )
            RtlCopyFromUser(Src, a3, 0x30u);
          else
            RtlCopyVolatileMemory(Src, a3, 0x30u);
          *((_QWORD *)&Src[0] + 1) = *((_QWORD *)StackBase + 20);
          *(_QWORD *)&Src[1] = *(_QWORD *)(*((_QWORD *)StackBase + 9) + 56LL);
          *((_QWORD *)&Src[1] + 1) = *((_QWORD *)StackBase + 26);
          LODWORD(Src[0]) = v16;
          if ( v8 )
            RtlCopyToUser(a3, Src, 0x30u);
          else
            RtlCopyVolatileMemory(a3, Src, 0x30u);
          v11 = 0;
        }
        else
        {
          v11 = -1073741820;
        }
      }
      goto LABEL_28;
  }
  v11 = -1073741637;
LABEL_28:
  SkobDereferenceObject((__int64)StackBase);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400addd0  mov     r11, rsp
0x1400addd3  mov     [r11+10h], rbx
0x1400addd7  mov     [r11+18h], rsi
0x1400adddb  push    rdi
0x1400adddc  push    r12
0x1400addde  push    r13
0x1400adde0  push    r14
0x1400adde2  push    r15
0x1400adde4  sub     rsp, 70h
0x1400adde8  mov     r13d, r9d
0x1400addeb  mov     r15, r8
0x1400addee  mov     esi, edx
0x1400addf0  xor     eax, eax
0x1400addf2  xorps   xmm0, xmm0
0x1400addf5  movups  [rsp+98h+Src], xmm0
0x1400addfa  movups  xmmword ptr [rsp+98h+var_48], xmm0
0x1400addff  movups  xmmword ptr [rsp+98h+var_48+0Ch], xmm0
0x1400ade04  mov     [r11+8], rax
0x1400ade08  mov     [r11-60h], rax
0x1400ade0c  mov     rax, gs:8
0x1400ade15  mov     r12b, [rax+60h]
0x1400ade19  cmp     rcx, 0FFFFFFFFFFFFFFFEh
0x1400ade1d  jnz     short loc_1400ADE3A
0x1400ade1f  mov     [r11+8], rcx
0x1400ade23  mov     rdi, gs:8
0x1400ade2c  mov     [r11-60h], rdi
0x1400ade30  mov     rcx, rdi
0x1400ade33  call    SkobReferenceObject
0x1400ade38  jmp     short loc_1400ADE70
0x1400ade3a  lea     rax, [rsp+98h+arg_0]
0x1400ade42  mov     [rsp+98h+var_70], rax
0x1400ade47  lea     rax, [rsp+98h+var_60]
0x1400ade4c  mov     [rsp+98h+var_78], rax
0x1400ade51  lea     r9, SkeThreadType
0x1400ade58  xor     r8d, r8d
0x1400ade5b  mov     dl, r12b
0x1400ade5e  call    SkobReferenceObjectByHandle
0x1400ade63  test    eax, eax
0x1400ade65  js      loc_1400ADFC5
0x1400ade6b  mov     rdi, [rsp+98h+var_60]
0x1400ade70  test    esi, esi
0x1400ade72  jz      short loc_1400ADEA5
0x1400ade74  cmp     esi, 0Ch
0x1400ade77  jz      short loc_1400ADE9D
0x1400ade79  cmp     esi, 11h
0x1400ade7c  jz      short loc_1400ADE95
0x1400ade7e  cmp     esi, 17h
0x1400ade81  jz      short loc_1400ADE8D
0x1400ade83  mov     ebx, 0C00000BBh
0x1400ade88  jmp     loc_1400ADFBB
0x1400ade8d  mov     r14d, 10h
0x1400ade93  jmp     short loc_1400ADEAB
0x1400ade95  mov     r14d, 1
0x1400ade9b  jmp     short loc_1400ADEAB
0x1400ade9d  mov     r14d, 4
0x1400adea3  jmp     short loc_1400ADEAB
0x1400adea5  mov     r14d, 30h ; '0'
0x1400adeab  mov     rbx, [rsp+98h+arg_20]
0x1400adeb3  mov     [rsp+98h+var_78], rbx
0x1400adeb8  mov     r9d, r13d
0x1400adebb  mov     r8, r15
0x1400adebe  mov     edx, esi
0x1400adec0  mov     rcx, [rsp+98h+arg_0]
0x1400adec8  call    NkQueryInformationThread
0x1400adecd  mov     r9, r13
0x1400aded0  mov     [rsp+98h+var_70], 0
0x1400aded9  mov     dword ptr [rsp+98h+var_78], eax
0x1400adedd  mov     r8, r14
0x1400adee0  mov     edx, 4
0x1400adee5  mov     rcx, rbx
0x1400adee8  call    IumSanitizeReturnLength
0x1400adeed  mov     ebx, eax
0x1400adeef  test    eax, eax
0x1400adef1  js      loc_1400ADFBB
0x1400adef7  test    esi, esi
0x1400adef9  jnz     loc_1400ADFBB
0x1400adeff  cmp     r13d, 30h ; '0'
0x1400adf03  jnb     short loc_1400ADF0F
0x1400adf05  mov     ebx, 0C0000004h
0x1400adf0a  jmp     loc_1400ADFBB
0x1400adf0f  mov     byte ptr [rsp+98h+arg_0], r12b
0x1400adf17  lea     r9, [rdi+0D8h]
0x1400adf1e  mov     rcx, r9
0x1400adf21  call    SkAcquireRundownProtection
0x1400adf26  test    al, al
0x1400adf28  jnz     short loc_1400ADF32
0x1400adf2a  mov     ebx, [rdi+11Ch]
0x1400adf30  jmp     short loc_1400ADF41
0x1400adf32  xor     edx, edx
0x1400adf34  mov     rcx, r9
0x1400adf37  call    SkReleaseRundownProtection
0x1400adf3c  mov     ebx, 103h
0x1400adf41  mov     r8d, 30h ; '0'; Size
0x1400adf47  mov     rdx, r15; Src
0x1400adf4a  lea     rcx, [rsp+98h+Src]; void *
0x1400adf4f  test    r12b, r12b
0x1400adf52  jz      short loc_1400ADF5B
0x1400adf54  call    RtlCopyFromUser
0x1400adf59  jmp     short loc_1400ADF60
0x1400adf5b  call    RtlCopyVolatileMemory
0x1400adf60  mov     rax, [rdi+0A0h]
0x1400adf67  mov     qword ptr [rsp+98h+Src+8], rax
0x1400adf6c  mov     rax, [rdi+48h]
0x1400adf70  mov     rcx, [rax+38h]
0x1400adf74  mov     qword ptr [rsp+98h+var_48], rcx
0x1400adf79  mov     rax, [rdi+0D0h]
0x1400adf80  mov     qword ptr [rsp+98h+var_48+8], rax
0x1400adf85  mov     dword ptr [rsp+98h+Src], ebx
0x1400adf89  mov     r8d, 30h ; '0'; Size
0x1400adf8f  lea     rdx, [rsp+98h+Src]; Src
0x1400adf94  mov     rcx, r15; void *
0x1400adf97  test    r12b, r12b
0x1400adf9a  jz      short loc_1400ADFA3
0x1400adf9c  call    RtlCopyToUser
0x1400adfa1  jmp     short loc_1400ADFA8
0x1400adfa3  call    RtlCopyVolatileMemory
0x1400adfa8  xor     ebx, ebx
0x1400adfaa  mov     [rsp+98h+var_64], ebx
0x1400adfae  jmp     short loc_1400ADFBB
0x1400adfb0  mov     ebx, eax
0x1400adfb2  mov     [rsp+98h+var_64], eax
0x1400adfb6  mov     rdi, [rsp+98h+var_60]
0x1400adfbb  mov     rcx, rdi
0x1400adfbe  call    SkobDereferenceObject
0x1400adfc3  mov     eax, ebx
0x1400adfc5  lea     r11, [rsp+98h+var_28]
0x1400adfca  mov     rbx, [r11+38h]
0x1400adfce  mov     rsi, [r11+40h]
0x1400adfd2  mov     rsp, r11
0x1400adfd5  pop     r15
0x1400adfd7  pop     r14
0x1400adfd9  pop     r13
0x1400adfdb  pop     r12
0x1400adfdd  pop     rdi
0x1400adfde  retn
0x1400fab6c  push    rbp
0x1400fab6e  sub     rsp, 30h
0x1400fab72  mov     rbp, rdx
0x1400fab75  xor     eax, eax
0x1400fab77  cmp     [rbp+0A0h], al
0x1400fab7d  setnz   al
0x1400fab80  mov     [rbp+30h], eax
0x1400fab83  mov     eax, [rbp+30h]
0x1400fab86  add     rsp, 30h
0x1400fab8a  pop     rbp
0x1400fab8b  retn
```
