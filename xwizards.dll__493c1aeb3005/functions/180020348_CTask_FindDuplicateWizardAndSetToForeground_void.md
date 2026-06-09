# CTask::FindDuplicateWizardAndSetToForeground(void)

- ea: `0x180020348`
- end: `0x180020425`
- name: `?FindDuplicateWizardAndSetToForeground@CTask@@AEAAHXZ`
- size: `221`
- prototype: `__int64 __fastcall(LPARAM lParam)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180024074`

## callees

- `0x18000ae04`
- `0x180020348`

## import_xrefs

- `USER32!GetParent` at `0x1800203a8`
- `USER32!GetParent` at `0x1800203bf`
- `USER32!GetParent` at `0x1800203a8`
- `USER32!GetParent` at `0x1800203bf`
- `USER32!SetForegroundWindow` at `0x1800203c8`
- `USER32!SetForegroundWindow` at `0x1800203dc`
- `USER32!SetForegroundWindow` at `0x1800203c8`
- `USER32!SetForegroundWindow` at `0x1800203dc`
- `USER32!FindWindowW` at `0x180020365`
- `USER32!FindWindowW` at `0x180020365`
- `USER32!IsWindow` at `0x180020396`
- `USER32!IsWindow` at `0x180020396`
- `USER32!EnumChildWindows` at `0x180020386`
- `USER32!EnumChildWindows` at `0x180020386`
- `USER32!ShowWindowAsync` at `0x1800203b6`
- `USER32!ShowWindowAsync` at `0x1800203d3`
- `USER32!ShowWindowAsync` at `0x1800203b6`
- `USER32!ShowWindowAsync` at `0x1800203d3`

## pseudocode

```c

```
