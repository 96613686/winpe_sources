# RaiseExecutionAbortedError(ABORT_AND_LCK_EXCEPTIONS)

- ea: `0x10044ace0`
- end: `0x10044aec5`
- name: `?RaiseExecutionAbortedError@@YAXW4ABORT_AND_LCK_EXCEPTIONS@@@Z`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x10044ac70`
- `0x10044ace0`
- `0x10044af90`
- `0x10044b040`

## import_xrefs

- `sqlmin!?IsExecutionAbortedDueToTmAbort@@YAHXZ` at `0x10044acf2`
- `sqlmin!?IsExecutionAbortedDueToTmAbort@@YAHXZ` at `0x10044acf2`
- `sqlmin!?RaiseSptViolationError@@YAXXZ` at `0x10044adab`
- `sqlmin!?RaiseSptViolationError@@YAXXZ` at `0x10044adab`
- `sqldk!SystemThread_TlsOffset` at `0x10044ad1a`
- `sqldk!SystemThread_TlsOffset` at `0x10044ad61`
- `sqldk!SystemThread_TlsIndex` at `0x10044ad11`
- `sqldk!SystemThread_TlsIndex` at `0x10044ad58`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10044ae8c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10044ae8c`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10044aea9`

## pseudocode

```c
int __fastcall RaiseExecutionAbortedError(unsigned __int8 a1)
{
  int v1; // ebx
  int v2; // edx
  __int64 v3; // rax
  __int64 v4; // rax
  int v5; // edx
  int v6; // ecx

  v1 = a1;
  if ( IsExecutionAbortedDueToAttention() )
  {
    if ( IsExecutionAbortedDueToTmAbort() )
    {
      RaiseTmAbortError((unsigned __int8)v1);
      __debugbreak();
    }
    v2 = 17;
LABEL_26:
    LODWORD(v3) = ex_raise(36, v2, 25, v1);
    return v3;
  }
  v3 = *(_QWORD *)(SystemThread_TlsOffset
                 + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
  if ( v3 )
  {
    if ( *(_BYTE *)(*(_QWORD *)(v3 + 56) + 8LL) )
    {
      LODWORD(v3) = SOS_Task::IsDelayAbortOn();
      if ( !(_DWORD)v3 )
      {
        v4 = *(_QWORD *)(SystemThread_TlsOffset
                       + *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex));
        if ( v4 )
        {
          switch ( *(_DWORD *)(*(_QWORD *)(v4 + 56) + 12LL) )
          {
            case 2:
              ex_raise(401, 74, 16, 3);
              break;
            case 3:
              ex_raise(401, 74, 16, 4);
              break;
            case 5:
              ex_raise(401, 74, 16, 5);
              break;
            case 0xA:
              v5 = 19;
              v6 = 12;
              goto LABEL_24;
            case 0xB:
              RaiseSptViolationError();
              break;
            case 0x64:
              v5 = 50;
              v6 = 405;
              goto LABEL_24;
            case 0x65:
              v5 = 49;
              v6 = 405;
              goto LABEL_24;
            case 0x66:
              ex_raise(405, 49, 16, 2);
              break;
            case 0x67:
              v5 = 51;
              v6 = 405;
              goto LABEL_24;
            case 0x68:
              v5 = 52;
              v6 = 405;
              goto LABEL_24;
            case 0x69:
              ex_raise(405, 52, 16, 2);
              break;
            case 0x6A:
              v5 = 53;
              v6 = 405;
              goto LABEL_24;
            case 0x6B:
              ex_raise(405, 51, 16, 2);
              break;
            case 0x6C:
              ex_raise(405, 51, 16, 3);
              break;
            case 0x6E:
              v5 = 43;
              v6 = 36;
LABEL_24:
              ex_raise(v6, v5, 16, 1);
              break;
            default:
              break;
          }
        }
        v2 = 2;
        goto LABEL_26;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x10044ace0  push    rbx
0x10044ace2  sub     rsp, 20h
0x10044ace6  movzx   ebx, cl
0x10044ace9  call    ?IsExecutionAbortedDueToAttention@@YAHXZ; IsExecutionAbortedDueToAttention(void)
0x10044acee  test    eax, eax
0x10044acf0  jz      short loc_10044AD08
0x10044acf2  call    cs:__imp_?IsExecutionAbortedDueToTmAbort@@YAHXZ; IsExecutionAbortedDueToTmAbort(void)
0x10044acf8  test    eax, eax
0x10044acfa  jnz     loc_10044AEBC
0x10044ad00  lea     edx, [rax+11h]
0x10044ad03  jmp     loc_10044AE97
0x10044ad08  mov     r8, gs:58h
0x10044ad11  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044ad18  mov     edx, [rax]
0x10044ad1a  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044ad21  mov     ecx, [rax]
0x10044ad23  mov     rax, [r8+rdx*8]
0x10044ad27  mov     rax, [rcx+rax]
0x10044ad2b  test    rax, rax
0x10044ad2e  jz      loc_10044AEB6
0x10044ad34  mov     rcx, [rax+38h]
0x10044ad38  cmp     byte ptr [rcx+8], 0
0x10044ad3c  jz      loc_10044AEB6
0x10044ad42  call    ?IsDelayAbortOn@SOS_Task@@SAHXZ; SOS_Task::IsDelayAbortOn(void)
0x10044ad47  test    eax, eax
0x10044ad49  jnz     loc_10044AEB6
0x10044ad4f  mov     r8, gs:58h
0x10044ad58  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10044ad5f  mov     edx, [rax]
0x10044ad61  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10044ad68  mov     ecx, [rax]
0x10044ad6a  mov     rax, [r8+rdx*8]
0x10044ad6e  mov     rax, [rcx+rax]
0x10044ad72  test    rax, rax
0x10044ad75  jz      def_10044ADA9; jumptable 000000010044ADA9 default case, cases 4,6-9,12-99,109
0x10044ad7b  mov     rcx, [rax+38h]
0x10044ad7f  mov     eax, [rcx+0Ch]
0x10044ad82  add     eax, 0FFFFFFFEh; switch 109 cases
0x10044ad85  cmp     eax, 6Ch
0x10044ad88  ja      def_10044ADA9; jumptable 000000010044ADA9 default case, cases 4,6-9,12-99,109
0x10044ad8e  lea     rdx, ?tiBit@CTypeInfo@@2V1@B; CTypeInfo const CTypeInfo::tiBit
0x10044ad95  cdqe
0x10044ad97  movzx   eax, ds:(byte_10044AF10 - 100400000h)[rdx+rax]
0x10044ad9f  mov     ecx, ds:(jpt_10044ADA9 - 100400000h)[rdx+rax*4]
0x10044ada6  add     rcx, rdx
0x10044ada9  jmp     rcx; switch jump
0x10044adab  call    cs:__imp_?RaiseSptViolationError@@YAXXZ; jumptable 000000010044ADA9 case 11
0x10044adb1  jmp     def_10044ADA9; jumptable 000000010044ADA9 default case, cases 4,6-9,12-99,109
0x10044adb6  mov     edx, 4Ah ; 'J'; jumptable 000000010044ADA9 case 2
0x10044adbb  mov     ecx, 191h
0x10044adc0  lea     r9d, [rdx-47h]
0x10044adc4  jmp     loc_10044AE86
0x10044adc9  mov     edx, 4Ah ; 'J'; jumptable 000000010044ADA9 case 3
0x10044adce  mov     ecx, 191h
0x10044add3  lea     r9d, [rdx-46h]
0x10044add7  jmp     loc_10044AE86
0x10044addc  mov     edx, 4Ah ; 'J'; jumptable 000000010044ADA9 case 5
0x10044ade1  mov     ecx, 191h
0x10044ade6  lea     r9d, [rdx-45h]
0x10044adea  jmp     loc_10044AE86
0x10044adef  mov     edx, 32h ; '2'; jumptable 000000010044ADA9 case 100
0x10044adf4  mov     ecx, 195h
0x10044adf9  jmp     loc_10044AE80
0x10044adfe  mov     edx, 33h ; '3'; jumptable 000000010044ADA9 case 103
0x10044ae03  mov     ecx, 195h
0x10044ae08  jmp     short loc_10044AE80
0x10044ae0a  mov     edx, 34h ; '4'; jumptable 000000010044ADA9 case 104
0x10044ae0f  mov     ecx, 195h
0x10044ae14  jmp     short loc_10044AE80
0x10044ae16  mov     edx, 34h ; '4'; jumptable 000000010044ADA9 case 105
0x10044ae1b  mov     ecx, 195h
0x10044ae20  lea     r9d, [rdx-32h]
0x10044ae24  jmp     short loc_10044AE86
0x10044ae26  mov     edx, 31h ; '1'; jumptable 000000010044ADA9 case 101
0x10044ae2b  mov     ecx, 195h
0x10044ae30  jmp     short loc_10044AE80
0x10044ae32  mov     edx, 31h ; '1'; jumptable 000000010044ADA9 case 102
0x10044ae37  mov     ecx, 195h
0x10044ae3c  lea     r9d, [rdx-2Fh]
0x10044ae40  jmp     short loc_10044AE86
0x10044ae42  mov     edx, 35h ; '5'; jumptable 000000010044ADA9 case 106
0x10044ae47  mov     ecx, 195h
0x10044ae4c  jmp     short loc_10044AE80
0x10044ae4e  mov     edx, 13h; jumptable 000000010044ADA9 case 10
0x10044ae53  lea     ecx, [rdx-7]
0x10044ae56  jmp     short loc_10044AE80
0x10044ae58  mov     edx, 33h ; '3'; jumptable 000000010044ADA9 case 107
0x10044ae5d  mov     ecx, 195h
0x10044ae62  lea     r9d, [rdx-31h]
0x10044ae66  jmp     short loc_10044AE86
0x10044ae68  mov     edx, 33h ; '3'; jumptable 000000010044ADA9 case 108
0x10044ae6d  mov     ecx, 195h
0x10044ae72  lea     r9d, [rdx-30h]
0x10044ae76  jmp     short loc_10044AE86
0x10044ae78  mov     edx, 2Bh ; '+'; jumptable 000000010044ADA9 case 110
0x10044ae7d  lea     ecx, [rdx-7]
0x10044ae80  mov     r9d, 1
0x10044ae86  mov     r8d, 10h
0x10044ae8c  call    cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10044ae92  mov     edx, 2; jumptable 000000010044ADA9 default case, cases 4,6-9,12-99,109
0x10044ae97  mov     r8d, 19h
0x10044ae9d  mov     r9d, ebx
0x10044aea0  lea     ecx, [r8+0Bh]
0x10044aea4  add     rsp, 20h
0x10044aea8  pop     rbx
0x10044aea9  jmp     cs:__imp_?ex_raise@@YAHHHHHZZ; ex_raise(int,int,int,int,...)
0x10044aeb6  add     rsp, 20h
0x10044aeba  pop     rbx
0x10044aebb  retn
0x10044aebc  movzx   ecx, bl
0x10044aebf  call    ?RaiseTmAbortError@@YAXW4ABORT_AND_LCK_EXCEPTIONS@@@Z; RaiseTmAbortError(ABORT_AND_LCK_EXCEPTIONS)
0x10044aec4  int     3; Trap to Debugger
```
